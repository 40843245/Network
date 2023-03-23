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
    
![image](https://user-images.githubusercontent.com/75050655/227242919-5a8b84c0-83c0-420b-a488-c602d647c7db.png)

    
 
 ## Ref
 
 ### About MAC
 https://en.wikipedia.org/wiki/Medium_access_control
 
 ### Details to ARP configures MAC.
 https://ithelp.ithome.com.tw/articles/10222979
 
 https://ithelp.ithome.com.tw/articles/10240142
 
 ### About ARP
 
 https://en.wikipedia.org/wiki/Address_Resolution_Protocol
 
