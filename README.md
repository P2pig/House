# Rpi 4 house

Trying integrate functions on a arm device:

- [main file] (./house)
- [A sample of simple factory pattern] (./simpFac)
- [build libray] (./build)

構想:

equip: rpi3 or 4

自能家具功能與實現：
	通過 手機App, 語音, 生物識別
	控制 門鎖, 燈光, 空調, 窗簾, 電視, 插座

模式：回家模式, 睡覺模式

架構：簡單工廠模式(smilar to char device driver in kernel)
      TCP服務器, 語音,人臉識別 功能設計成每個練表的節點 形成控制工廠
      燈光,門鎖,窗簾 成為節點 成為設備端的工廠

      優勢: 曾新功能只須 增加新練表節點, 穩定擴展能力

控制空調：紅外線邊解碼單元 (支持遙控器的學習和替代功能）

窗簾：    433m射頻單元 來實現遠程控制

人臉識別：使用opencv or facial regconize platform(華為人工智能語音平台人臉識別)

語音：    使用3320的二次開發, keil環境中閱讀廠家給的代碼, 找出識別代碼 對串口通訊進行修改並整合到樹莓派的串口通信中
