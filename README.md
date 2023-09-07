# vivekstoken
This is a smart contrct wrote in solidity language in which I had created a token of my name as vivektoken and I have used the mint
and the burn functions in my contract.

# description
Solidity is a popular language present for making the smart contracts in the ethereum blockchain which are self excutable.

# how to run
Copy this code and go to the remix ide and run the this code.

        pragma solidity ^0.8.0;
      
        contract MyToken {
          string public name;
          string public symbol;
          uint256 public totalSupply;
      
          mapping(address => uint256) public balances;
      
          constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
              name = _name;
              symbol = _symbol;
              totalSupply = _totalSupply;
              balances[msg.sender] = _totalSupply;
          }
      
          function mint(address _to, uint256 _value) public {
              totalSupply += _value;
              balances[_to] += _value;
          }
      
          function burn(address _from, uint256 _value) public {
              require(balances[_from] >= _value, "Insufficient balance");
              totalSupply -= _value;
              balances[_from] -= _value;
          }
      }
