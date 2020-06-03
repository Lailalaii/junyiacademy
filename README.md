# junyiacademy
remote test for software engineer

# 題目 #

1. 
    - (A)請寫一個程式把裡面的字串反過來。 
    - (B)請寫一個程式把裡面的字串,每個單字本身做反轉,但是單字的順序不變。 
    >舉例 
    >f ( "junyiacademy" ) == "ymedacaiynuj" f ( "flipped class room is important" ) == "deppilf ssalc moor si tnatropmi" 

        //1(A)
        function f(string){
            var myArray = [];
            for (var i = string.length; i >0; i--){
            myArray += string.substr((i-1),1);
            }
            return myArray;
         }
         console.log(f("junyiacademy"));
         //1(B)這個功能我沒有學過也沒有看過，不確定要怎麼寫。我猜應該有一個可以把字母反轉的指令，搭配前面的照順序輸出字串方法即可完成任務。
---
2. 請寫一個程式,Input 是一個數字,Output 是從 1 到這個數字,扣除掉所有 3 的 
倍數以及 5 的倍數,但是需要保留同時是 3 和 5 的倍數的總數字數。 
    >舉例
    > Input:15 所有的數字是:1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15 其中 3, 6, 9, 12 被剔除;5, 10 被剔除;但是 15 被保留 所以剩下來的數字是 1, 2, 4, 7, 8, 11, 13, 14, 15,因此 Output:9 
    
        function fif(number){
            var myArray = [];
            for (let i = 1; i <= number; i++){
            if (((i % 3 !== 0) & (i % 5 !== 0)) || (i % 15 === 0 )){
            myArray.push(i)};
            }
            return myArray.length;
        }

        console.log(fif(15))

---
3. 房間裡有三個袋子,一個只裝鉛筆,一個只裝原子筆,第三個有鉛筆也有原子筆。袋子是不透明的,單從袋子的外表上看不出任何差異,你不知道哪個袋子裝什麼。除了袋子上各貼了一個標示("鉛筆"、"原子筆"、"混和"),且標示都是錯的(e.g. 標示鉛筆的袋子可能是混和的或是只裝原子筆)。你只能選一個袋子,拿出裡面一支筆,看是鉛筆還是原子筆,然後你要推論出這三個袋子分別的情況。請列出你的作法,以及解釋為什麼這樣可以找到答案。 

    A: 選”混和”的袋子，    
    有兩種情況:    
    Case 1:拿出”鉛筆”    
    代表標示混和的袋子全是鉛筆，那”原子筆”標籤的袋子原本有兩種可能(“鉛筆”或”混和”)，現在只剩一個可能”混和”，而最後”鉛筆”標籤的袋子則是原子筆。結果:     
    標籤:實際=> 混和:鉛筆, 原子筆:混和, 鉛筆:原子筆
    
    case 2:拿出”原子筆”,    
    同理，結果:    
    標籤:實際=> 混和:原子筆, 鉛筆:混和, 原子筆:鉛筆

4. 有三個人一起到迪士尼遊玩,中午肚子餓了,去餐廳點了一份現在最夯的冰雪奇緣雙人組,要價 900 元,付錢後,服務生發現今天套餐大特價,只要 750 元,因此服務生應該退還 150 元給這三個人,但是這位服務生一時鬼迷心竅,決定暗槓 60元,只退了 90 元給這三個遊客。那麼:三人各出 300 元 - 服務生還給他們一人 30 元 = 三人各出 270 元。270 元 × 3 人+ 服務生私吞的 60 元 = 810 + 60 = 870 !? 怎麼不是 900 元呢?還有 30 元去哪了呢?請用敘述的方式,儘量清楚解釋問題出在哪裡。 

    A:    
    原本預計花的錢:900,    
    特價後應該花的錢:750,    
    服務生暗槓的錢:60,    
    預計要花卻退還(沒花)的錢:90,    
    
    原本預計花的錢=(特價後應該花的錢+服務生暗槓的錢)+預計要花卻退還(沒花)的錢    
        900      =(    750       +     60      )+        90    
    原本預計花的錢=           最後花的錢         +預計要花卻退還(沒花)的錢    
        900      =           270 * 3           +        90    
    結論:這裡所犯的邏輯謬誤是服務生吞的錢應該是在270 * 3裡面。也可以想成服務生如果藏越多錢，他們最後就要花越多錢，所以式子本身就是有問題的。
