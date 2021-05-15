### Audit log

By newbie solidity user -DongData
- *Accessible selfdestruct:* 无
- *Bad randomness:* 无
- *DoS (induction variable overflow):* 无 a variable that changes inside a loop seems easy to overflow (e.g., is a uint8), which can cause unbounded iteration.
- *DoS (unbounded operation):* 无
- *DoS (wallet griefing):* 没找到，send失败throw -需要学习进阶考虑 Ethereum Virtual Machine execution model, particularly around gas costs.
- *Reentrancy:* 没找到
- *Reentrancy (Constantinople):* 对this和is的用法不确定，看不出来有没有 the contract makes an external call that seems safe against reentrancy under the standard, expensive gas model for SSTORE instructions, but possibly not under a model that makes SSTOREs on the same address cheaper.
- *Tainted delegatecall:*  自动检测无 https://contract-library.com/contracts/Rinkeby/0x8C847A0E6B48C6E1D77D24A33127443F0C607B02
- *Tainted ether value:* 没找到
- *Tainted owner variable:* 无
- *Tainted selfdestruct:* 无
- *Tainted storage index:* 有SSTORE，需要确认是否tainted SSTORE instructions that can write to locations that may be changed via external calls. https://ethervm.io/decompile/rinkeby/0x8C847A0E6B48C6E1D77D24A33127443F0C607B02

Resource used:
[checklist](https://github.com/cryptofinlabs/audit-checklist)
[coverage](https://github.com/sc-forks/solidity-coverage)
[slither, solidity best practice](https://consensys.github.io/smart-contract-best-practices/security_tools/)
