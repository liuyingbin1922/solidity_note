## storage && memory

在solidity 中，storage && memory 可以存储变量。
storage 是指可以永久存储在区块链中的变量，memory 是指临时的变量；

不过大多数的时候，你是用不到这两个变量的，可以这么理解，storage是在函数外部使用的，memory 是在函数内部使用的；

```js

  function moveGoods(uint _antId , uint _originHouseId, uint _targetHouseId) {
	require(msg.sender == antToOwner[_antId], "只能用自己的蚂蚁搬东西");
	require(msg.sender == houseToOwner[_originHouseId], "只能给自己家搬东西");
	require(msg.sender == houseToOwner[_targetHouseId], "只能给自己家搬东西");
	House storage originHouse = houses[_originHouseId];
	House storage targetHouse = houses[_targetHouseId]; 
  }
```


