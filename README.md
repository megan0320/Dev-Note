# Google Cloud IoT Platform
利用Google Cloud Platform的功能打造IoT Platform。由裝置的角度出發、資料庫串接到資料分析，由近到遠介紹。

## Device connection
透過**Cloud IoT Core**及**Cloud Pub/Sub**連接裝置到Google Cloud Platform。

![Image text](https://github.com/megan0320/Dev-Note/blob/main/device_connection.PNG)

* **Cloud IoT Core**是IoT裝置的管理平台，連接並取得裝置資訊並，讓使用者可以管理IoT裝置，並連接其他服務(ex. [資料處理](https://gdgcloud-taipei.gitbook.io/google-cloud-platform-in-practice/google-cloud-shang-de-da-zi-liao-chu-li-fu-wu/cloud-dataflow/cloud-dataflow-jian-jie)、[微服務](https://medium.com/learn-or-die/gcp-cloud-functions-%E5%88%9D%E6%8E%A2-%E4%B8%BB%E6%8E%A7%E5%8F%B0-9c4f88adc315))建構物聯網系統。
* **Cloud Pub/Sub**是message service，主要用途是讓每個獨立使用者/應用間能透過 Publish-Subscribe的模式來進行訊息交換與溝通。
* 實作練習: 透過MQTT Example Device傳送訊息(ex.溫度)到Example Server :[ A Tour of Cloud IoT Core](https://codelabs.developers.google.com/codelabs/cloud-iot-core-overview#5)，result: [practice](https://console.cloud.google.com/cloudpubsub/subscription/detail/tour-sub?project=ask-go-test&cloudshell=false)

## Database
當IoT Core和Pub/Sub得到裝置資訊後，透過**Cloud Functions**將連接資料庫(**Firestore**)，也可以讓其他應用讀取/寫入資料。

![Image text](https://github.com/megan0320/Dev-Note/blob/main/gcp_connection.PNG)

* **Cloud Functions**:  可以將那些簡單且單一的功能附加在從Cloud Pub/Sub送出的 events 上。當 event 發生的時候，Cloud Functions執行指令 (ex.修改 Database 裡面的資料、將檔案新增至儲存系統)  [Cloud Functions 的介紹與應用](https://ikala.cloud/cloud-functions-introduction/)
* **Cloud Firestore**:是 Google 所提供的新一代即時資料庫，延續 RealTime Database 的高效率以及低延遲性，可以即時監聽資料庫的變化，並同步有使用到資料庫的各個application  [認識 Cloud Firestore](https://ikala.cloud/cloud-firestore-cloud-native-nosql-introduction/)

*實做練習: 透過Firestore連結Cloud Functions傳送資料到IoT device上 [Using Firestore with Cloud IoT Core for Device Configuration](https://www.cloudskillsboost.google/focuses/2767?locale=es&parent=catalog&qlcampaign=onair318-37) & [將感測資訊經由 IoT Studio 傳送到 Google Firebase 服務](https://oranwind.org/-iot-studio-jiang-gan-ce-zi-xun-jing-you-iot-studio-chuan-song-dao-google-firebase-fu-wu/)，result: [practice](https://console.cloud.google.com/iot/locations/us-central1/registries/config-demo/devices/details/sample-device/history?authuser=0&project=ask-go-test)

*實做練習: : use the Firebase SDK for Google Cloud Functions to improve a Chat Web app and how to use Cloud Functions to send notifications to users of the Chat app. [Cloud Functions for Firebase](https://firebase.google.com/codelabs/firebase-cloud-functions?hl=en&continue=https%3A%2F%2Fcodelabs.developers.google.com%2F%3Fcat%3Dfirebase#0)

*[撰寫由PubSub觸發並上傳到Firestore的Function](http://192.168.1.64/tiki-index.php?page=GCP+IoT+to+database)

## Data Analysis
若有資料分析需求，可以使用**Big Query**將資料進一步分析、藉由**Data Studio**產出視覺化報表。

![Image text](https://github.com/megan0320/Dev-Note/blob/main/gcp_connection2.PNG)

* **Big Query** : 大資料儲存與查詢的服務，可以提供大量的資料儲存，且以結構化查詢(SQL)方式查詢儲存的資料，並且可以支援資料表之間的Join動作  [BigQuery簡介](https://gdgcloud-taipei.gitbook.io/google-cloud-platform-in-practice/google-cloud-shang-de-da-zi-liao-chu-li-fu-wu/bigquery/bigquery-jian-jie)
* **Data Studio** : 提供強大的視覺化編輯工具，只要把資料匯入進來，就可以產生報表 [使用 Google Data Studio 數據分析工具，輕鬆打造 Google Analytics 視覺化報表](https://jerrynest.io/google-data-studio/)
- [demo site](https://datastudio.google.com/reporting/f1837c75-6dd4-4355-9966-ca1785d14302/page/aD0ZB) : 提供各種類型報表範本 ex. Firebase Report


