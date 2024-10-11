CoinGecko API集成

端点1 - **/tickers**（市场信息）

接口：/pub/tickers

完整url：https://openapi.grovex.io/pub/tickers

请求方式：GET

响应说明：

| 名称            | 数据类型 | 说明                                                      |
| --------------- | -------- | --------------------------------------------------------- |
| ticker_id       | string   | 行情标识符，使用分隔符分隔基础资产和目标资产，例如ethusdt |
| base_currency   | string   | 基础加密资产的符号                                        |
| target_currency | string   | 目标加密资产的符号                                        |
| last_price      | decimal  | 基于目标资产的基础资产的最后成交价                        |
| base_volume     | decimal  | 交易对的24小时交易量（单位为基础资产）                    |
| target_volume   | decimal  | 交易对的24小时交易量（单位为目标资产）                    |



端点2 - **/orderbook**（订单簿深度详细信息）

接口：/pub/newOrderBook

完整url：https://openapi.grovex.io/pub/newOrderBook

示例url：https://openapi.grovex.io/pub/newOrderBook?symbol=btcusdt&depth=100

请求方式：GET

请求参数：

| 名称   | 类型    | 状态 | 说明                                                         |
| ------ | ------- | ---- | ------------------------------------------------------------ |
| symbol | string  | 必填 | 交易对标识符，如btcusdt，小写                                |
| depth  | integer | 选填 | 订单簿深度数量：[0, 100, 200]。0返回完整深度。深度=100表示买卖两侧各50个。不填默认为0 |

**响应说明：**

| 名称 | 数据类型 | 说明                                           |
| ---- | -------- | ---------------------------------------------- |
| bids | decimal  | 包含两个元素的数组，分别为每个买单的出价和数量 |
| asks | decimal  | 包含两个元素的数组，分别为每个卖单的出价和数量 |