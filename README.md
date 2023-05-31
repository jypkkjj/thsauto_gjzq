# thsauto
同花顺自动下单工具

```
python .\server.py  192.168.0.116 5000 C:\Users\match\Desktop\THS\xiadan.exe
```
- 查询资金账户  
http://192.168.0.116:5000/thsauto/balance  
- 查询持仓  
http://192.168.0.116:5000/thsauto/position  
- 买入下单  
http://192.168.0.116:5000/thsauto/buy?stock_no=600000&price=10.00&amount=100  
- 卖出下单  
http://192.168.0.116:5000/thsauto/sell?stock_no=600000&price=10.00&amount=100  
- 科创板买入下单  
http://192.168.0.116:5000/thsauto/buy/kc?stock_no=688819&price=40.00&amount=200  
- 科创板卖出下单  
http://192.168.0.116:5000/thsauto/sell/kc?stock_no=688819&price=40.00&amount=200  
- 查询未成订单  
http://192.168.0.116:5000/thsauto/orders/active  
- 查询已成订单  
http://192.168.0.116:5000/thsauto/orders/filled  
- 撤单  
http://192.168.0.116:5000/thsauto/cancel?entrust_no=2060704404  
- 关闭同花顺客户端  
http://192.168.0.116:5000/thsauto/client/kill  
- 重启同花顺客户端  
http://192.168.0.116:5000/thsauto/client/restart  

[下单客户端地址](https://www.gjzq.com.cn/main/download.html)

示范：
```
from thsauto import ThsAuto
auto = ThsAuto()
auto.bind_client()
#获取持仓
print(auto. get_position())
#获取账户信息
print(auto.get_balance())
#下买单
auto.buy(‘601288’, 100, 5.00):
#下卖单
auto.sell(‘601288’, 100, 5.00):
下单成功后会返回委托编号供撤单使用
#撤单
auto.cancel("下单返回的委托编号")


print("Hello, World!");
```
