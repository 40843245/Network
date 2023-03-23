# Relation bewteen devices
## Objectives
In this article, I will discuss 
  
    1) ID of a computer MAC.
    2) How an OS identifies a computer -- through ARP.
    
 ## MAC (Media Access Control)
 I will NOT discuss the word MAC OS.
 
 Let's get started with a figure.
 ![image](https://user-images.githubusercontent.com/75050655/227235276-cf138917-46d3-4f7b-95cb-2583a08b8f2f.png)
 
 The above figure illustrates the relationshop of MAC and NIC (Network Interface Card). 
 
 MAC is an ID card of NIC. They are unique. That is to say,
 
 Each NIC must have exactly one MAC and the following statements are always true.
 
 Different NIC must have different MAC.
 
 Difference MAC must also have different NIC. 
 
 However, a computer can have many different NIC (especially for earlier computers, we will discuss it later).
 
 Thus, we can imply that a computer may contain many different MAC.
 
 It does NOT easily understand. Why can a computer uses many different MAC?
 
    <b>NOPE!!!</b> 
    
    A computer can only use at most one MAC at one time.
    
    However, a computer can contain many different MAC.
    
The issue comes. How to configure what MAC the computer will use?

    It will brings up the next section ( 2) How an OS identifies a computer -- through ARP.)
    
    The solution is ARP.
    
    
 NOTE that 
 
 1) Each computer may have many NIC.

![image](https://user-images.githubusercontent.com/75050655/227244074-df43988b-418a-46de-bda2-e19cd7f1362a.png)

The text of figures is 

### English version (original text)

    The number of NICs a computer has depends on the motherboard’s slot capacity and the operating system/driver related limits. Most decent OS/driver software should be able to take anywhere from 1 to 8 or basically unlimited numbers of NICs1. Newer server motherboards may have multiple network interfaces built-in

### Japanese version

NOTE that it is translate by google translator. Thus, it may NOT be fully expressed.

Welcome to translate it and leave it in branches if you can.


    コンピューターに搭載されている NIC の数は、マザーボードのスロット容量とオペレーティング システム/ドライバー関連の制限によって異なります。 ほとんどの適切な OS/ドライバー ソフトウェアは、1 から 8 までの任意の場所、または基本的に無制限の数の NIC を使用できるはずです1。 新しいサーバーのマザーボードには、複数のネットワーク インターフェイスが組み込まれている場合があります。
    
### Chinese version

    一台計算機的 NIC 數量取決於主板的插槽容量和操作系統/驅動程序相關的限制。 大多數體面的操作系統/驅動程序軟件應該能夠使用 1 到 8 個或基本上無限數量的 NIC1。 較新的服務器主板可能內置多個網絡接口



2) Furthermore, most  modern computer does NOT need extra NIC since it is integrated.
    
![image](https://user-images.githubusercontent.com/75050655/227242919-5a8b84c0-83c0-420b-a488-c602d647c7db.png)

    
 
 ## Ref
 
 ### About MAC
 https://en.wikipedia.org/wiki/Medium_access_control
 
 ### Details to ARP configures MAC.
 https://ithelp.ithome.com.tw/articles/10222979
 
 https://ithelp.ithome.com.tw/articles/10240142
 
 ### About ARP
 
 https://en.wikipedia.org/wiki/Address_Resolution_Protocol
 
