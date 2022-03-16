# Google Cloud IoT Platform
利用Google Cloud Platform的功能打造IoT Platform。由裝置的角度出發、資料庫串接到資料分析，由近到遠介紹。

Device connection
透過Cloud IoT Core及Cloud Pub/Sub連接裝置到Google Cloud Platform。



Cloud IoT Core是IoT裝置的管理平台，連接並取得裝置資訊並，讓使用者可以管理IoT裝置，並連接其他服務(ex. 資料處理、微服務)建構物聯網系統。
Cloud Pub/Sub是message service，主要用途是讓每個獨立使用者/應用間能透過 Publish-Subscribe的模式來進行訊息交換與溝通。
* 實作練習: 透過MQTT Example Device傳送訊息(ex.溫度)到Example Server : A Tour of Cloud IoT Core，result: practice

Database
當IoT Core和Pub/Sub得到裝置資訊後，透過Cloud Functions將連接資料庫(Firestore)，也可以讓其他應用讀取/寫入資料。



 Cloud Functions:  可以將那些簡單且單一的功能附加在從Cloud Pub/Sub送出的 events 上。當 event 發生的時候，Cloud Functions執行指令 (ex.修改 Database 裡面的資料、將檔案新增至儲存系統)  Cloud Functions 的介紹與應用
Cloud Firestore:是 Google 所提供的新一代即時資料庫，延續 RealTime Database 的高效率以及低延遲性，可以即時監聽資料庫的變化，並同步有使用到資料庫的各個application 認識 Cloud Firestore

*實做練習: 透過Firestore連結Cloud Functions傳送資料到IoT device上 Using Firestore with Cloud IoT Core for Device Configuration & 將感測資訊經由 IoT Studio 傳送到 Google Firebase 服務，result: practice

*實做練習: : use the Firebase SDK for Google Cloud Functions to improve a Chat Web app and how to use Cloud Functions to send notifications to users of the Chat app. Cloud Functions for Firebase 

*撰寫由PubSub觸發並上傳到Firestore的Function

Data Analysis
若有資料分析需求，可以使用Big Query將資料進一步分析、藉由Data Studio產出視覺化報表。


Big Query : 大資料儲存與查詢的服務，可以提供大量的資料儲存，且以結構化查詢(SQL)方式查詢儲存的資料，並且可以支援資料表之間的Join動作 BigQuery簡介
Data Studio : 提供強大的視覺化編輯工具，只要把資料匯入進來，就可以產生報表 使用 Google Data Studio 數據分析工具，輕鬆打造 Google Analytics 視覺化報表
demo site : 提供各種類型報表範本 ex. Firebase Report
*參考資料: Build a Weather Station using Google Cloud IoT Core and MongooseOS

