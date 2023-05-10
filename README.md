
## Ali_Khatami_Solidity12(learning from the video of Pattrick Collins)

### SafeMath,Overflow,Checking and the unchecked keyword

```safeMath.sol``` is one of the most common library that was used for the longest time<br>

![e5](https://github.com/C191068/Ali_Khatami_Solidity12/assets/89090776/d607da0a-ea54-47fe-b289-94b589d89838)
Figure1: we ahve created a new file known as ```akrkSafeMathTester.sol```<br>

```SafeMath``` was all over the place before version ```0.8``` of solidity and now it is almost in no contracts <br>

here is the code below:

```
//SPDX-License-Identifier:MIT

pragma solidity ^0.6.0;

contract akrkSafeMathTester{
    uint8 public largeNumber = 255 ;
}

```

![e6](https://github.com/C191068/Ali_Khatami_Solidity12/assets/89090776/c35cbd53-c5c6-4402-9ce2-f9358d84da41)
figure1: when we will deploy the above code we will get the above output
