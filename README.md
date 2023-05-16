
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


we modify the code below :

```
//SPDX-License-Identifier:MIT

pragma solidity ^0.6.0;

contract akrkSafeMathTester{
    uint8 public largeNumber = 255 ;

    function sum() public{

        largeNumber= largeNumber +1;

    }
}

```

![e7](https://github.com/C191068/Ali_Khatami_Solidity12/assets/89090776/24bb05f0-0640-4900-9d08-d7bcfaeb907b)
Figure2:when we deploy the above contract we see when we click the orange color ```sum``` button due to gas calling function <br>
the clicking the blue color ```largeNumber``` button instead of getting result ```256``` we are getting ```0``` <br>


This happens because prior to version ```0.8``` of solidity , unsigned integers and integers ran on thsi concept of being ```unchecked``` <br>
```unchecked``` means if we pass the upper limit of the  number it would just start back from the lowest number it could be <br>

So one of the most popular library was the above SafeMath library of the above code was basically use to make sure that we are not crossing the maximaum limt <br>
of an uint256 number<br>

![e8](https://github.com/C191068/Ali_Khatami_Solidity12/assets/89090776/fc5c31f0-3824-4d0a-ba83-ed81d3dfac10)
Figure3: after clicking the ```largeNumber``` button when we click the ```sum``` button it gives error at the console<br>

because at solidity version 0.8.0 and above it can automatically checked whether we are doing overflow or underflow on avariable<br>

on the other hand version 0.76 and below can't automatically checked whether we are doing overflow or underflow on avariable<br>

to revert back to the unchecked version we have done following changes in the code:

```
//SPDX-License-Identifier:MIT

pragma solidity ^0.8.0;

contract akrkSafeMathTester{
    uint8 public largeNumber = 255 ;

    function sum() public{

        unchecked{largeNumber= largeNumber +1;}

    }
}
```



![e9](https://github.com/C191068/Ali_Khatami_Solidity12/assets/89090776/4cdb776f-188b-44ce-a156-0e558066d03f)
Figure4: and thus now it is not showing any error when we click the ```sum``` button after clicking the ```largeNumber``` button <br>


```unchecked``` keyword makes our gas a little bit more efficient <br>








