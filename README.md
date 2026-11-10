# ble-panel

用網頁讀取 BLE 裝置 ID（Web Bluetooth），可在 iOS 的 **Bluefy** App 中開啟。

## 使用方式

1. 將本 repo 透過 HTTPS 提供（例如開啟 GitHub Pages：Settings → Pages → Branch 選擇此分支 / root）。
2. 在 iPhone 上開啟 Bluefy，輸入網址，例如 `https://<帳號>.github.io/ble-panel/`。
3. 按「搜尋附近裝置」會持續搜尋 20 秒（可按「停止」），列出所有收到廣播的裝置：名稱、ID、RSSI、服務 UUID、製造商資料，依訊號強弱排序；可用名稱篩選過濾。需瀏覽器支援 `requestLEScan`。
4. 或按「掃描並選擇裝置」，在彈出清單中選擇裝置，即可看到裝置 ID。
5. 勾選「連線並讀取 GATT」時，會額外列出服務 UUID，以及 Device Information（0x180A）中的製造商、型號、序號等。

Android / 桌機的 Chrome、Edge 也可直接使用。

## 注意

- Web Bluetooth 基於隱私**不提供 MAC 位址**；`device.id` 是瀏覽器為此網站產生的識別碼，同一裝置在同一網站下通常固定。
- 若需要真正的硬體識別，請讀取裝置的序號（Serial Number 特徵值）或自訂 GATT 特徵。
- 已讀取的裝置資料只存在本機瀏覽器（localStorage）。
