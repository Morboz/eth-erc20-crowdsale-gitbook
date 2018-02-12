### ERC20标准
   先介绍下EIP，全称是Ethereum Improvement Proposals，以太坊改善建议。任何人都可以在Github上提建议，你的建议有可能被采纳，也有可能被拒绝。
   
   其中代号为20的一项是2015年11月提出的，是对代币定义一个标准的提议，否则不同的代币要定制不同的钱包，使用不同的操作方式，非常麻烦。
   
   ERC20代币标准其实就是定义的合约的接口，由几个方法和事件组成。
```
// https://github.com/ethereum/EIPs/issues/20
  contract ERC20 {
      // 返回token的总供应量。
      function totalSupply() constant returns (uint totalSupply);
      // 返回地址是_owner的账户的账户余额。
      function balanceOf(address _owner) constant returns (uint balance);
      // 转移_value的token数量到的地址_to，并且必须触发Transfer事件。 如果_from帐户余额没有足够的令牌来支出，该函数应该被throw。
      function transfer(address _to, uint _value) returns (bool success);
      // 从地址_from发送数量为_value的token到地址_to,必须触发Transfer事件。
      function transferFrom(address _from, address _to, uint _value) returns (bool success);
      // 允许_spender多次从您的帐户取回最高达_value金额。 如果再次调用此函数，它将以_value覆盖当前的余量。
      function approve(address _spender, uint _value) returns (bool success);
      // 返回_spender仍然被允许从_owner提取的金额。
      function allowance(address _owner, address _spender) constant returns (uint remaining);
      // 当token被转移(包括0值)，必须被触发。
      event Transfer(address indexed _from, address indexed _to, uint _value);
      // 当任何成功调用approve(address _spender, uint256 _value)后，必须被触发。
      event Approval(address indexed _owner, address indexed _spender, uint _value);
    }
```
   大部分Ethereum主要代币符合ERC20标准。
   一些代币包括描述代币合约的进一步信息：
```
    string public constant name = "Token Name";  // 代币名称
    string public constant symbol = "SYM";		 // 代币符号
    uint8 public constant decimals = 18;  		 // 小数点位数
```

相关链接：

   [https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md]
   [https://theethereum.wiki/w/index.php/ERC20_Token_Standard#The_ERC20_Token_Standard_Interface]
   [http://blog.csdn.net/diandianxiyu_geek/article/details/78082551]
