# VirtualRealityPortalNetwork
Unityアセットです、VRMをサーバーにアップロードしたりダウンロードしたりしてほぼすべてのプラットフォームで動くVRM補助系のシステム
## More information   

（多分）ほぼ全プラットフォームでVRMがImportできるように一応作ってます 
今回のバージョンでは複数体のモデルを読み込むことができます  
これについてのフィードバックやアイディアなどもらえると嬉しいです  
(一部のフィードバックやアイデアは技術力がないのでできないかもしれないです、頑張りたいけど)


## How to use  
https://myfirstfb-68d49.firebaseapp.com/src/about.html    
対応バージョン
Windows10, Unity2018.2.5+

以下のunitypackageが必要
- UniVRM (Ver0.43 + ) 
- Firebase Storage / Auth / Database in Firebase Unity SDK 5.2.1 +
  
以下がセッテング方法  
(https://myfirstfb-68d49.firebaseapp.com/src/about.html に画像つきであります)  
- Unityで新規プロジェクトを開く  
- Editメニュー内のProject Settings/Playerを押してPlayer Settingsを開く  
- Other Settings内のConfigurationにあるScripting Runtime Version、Api Compatibility Levelを.Net 4.xに変更する  
- Firebase Auth,Database,Storage、UniVRMをインポートする  
- VRP_VRM_Importerをインポートする  
- 3DObjectのPlaneを配置し、カメラのZ座標を-5程度にする(ここは後で適宜調整してください)  
- 一度UIのtext - Text Mesh Proを作り出てくるインストーラのボタン2つとも押してインポートを済ませておく  
- Assets/VRP/Prefab/PutSceneにあるモノとAssets/VRP/Prefab/QRListExtensionにあるものをシーンに入れる  
- ヒエラルキー内のGameObjectの設定をする  
- ModelStorageのList NodeにAssets/VRP/Prefab/QRExtension/Nodeを、Target Listにヒエラルキー内QRCanvas/Scroll View/ViewPoint/Contentを入れる  
- AuthのEmailFieldにヒエラルキー内GUICanvas/EmailFieldを、PasswordFieldにGUICanvas/PasswordFieldをアタッチする  
- GUICanvas/EmailFieldのOnValueChangedにAuthを入れFunctionをEmailAuth.CopyEmail()を指定する、同様にPasswordFieldではEmailAuth.CopyPassword()を指定する  
- ヒエラルキー内GUICanvasにあるSign In からUploaderまで選択し、Inspector内On Click()にAuthをアタッチする  
- 以下の通りにOn Clickの設定をする  
<table>
            <thead>
          <tr>
              <th>Button Object</th>
              <th>OnClick Function</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td>Sign in</td>
              <td>SignInProcess</td>
          </tr>
          <tr>
              <td>Create</td>
              <td>CreateAccountProcess</td>
          </tr>
          <tr>
              <td>SignOut</td>
              <td>SignOutProcess</td>
          </tr>
          <tr>
              <td>UserInfo</td>
              <td>ShowUserInfo</td>
          </tr>
          <tr>
              <td>Loader</td>
              <td>LoadModelFromServer</td>
          </tr>
          <tr>
              <td>Uploader</td>
              <td>UploadModelToServer</td>
          </tr>
      </tbody>
          </table>
- ヒエラルキー内QRCanvas/RefreshButtonのOnClickにGameObjectのModelStorageをアタッチ、Modelstorage.AddListを設定する  
- これにて一通りの設定が完了です  
- Extra : ModelStorageにAssets/VRP/Scripts/Test/Runner.csをアタッチするとaキーで全モデルをグローバル座標(0，0，0)に呼び出せます（要認証とモデルロード  
  
### Upload model

一応開発者本人が立てているサーバがあります（Firebase）
WebからのVRMファイルアップロードができるようになっています  
以下のURLにアクセスして、Email　Signin後ページ下部にあるアップロードフォームよりモデルをアップロードしてください　　
https://myfirstfb-68d49.firebaseapp.com/


## License  
VRPN based on Apache 2.0 License
 See [Here](https://github.com/yuzuka4573/VirtualRealityPortalNetwork/blob/master/LICENSE)
   
   
## History
 |Version|data|Info|
 |---|---|---|
 |Version 1.1.0/1.2.0 Preview |2018/09/13 |すべての始まり ILI_Update|  
 |Version 1.3.0/1.3.1 Preview |2018/09/19 |コード再構築と安定性強化、Uploader完備 Mer_Update|
 |Version 1.3.2 Preview |2018/09/25 |疲れから来た誤字のオンパレード修正アップデート|
 |Version 1.4.0 SnapShot |2018/09/28 |VR関連業界からの挑戦状、対抗策試験運用 Pic_Update|
 |Version 1.4.1 Preview |2018/09/29 |テスト用のシーン整備、コードの修正もしました "2Dcode Function Now Active!!" Pic_Update|
 |Version 1.4.2 Preview |2018/09/30 |リスト表示関連のコード修正　UIの修正 "2Dcode Function Now Active!!" Pic_Update|
 |Version 1.4.3 |2018/12/21 |2ヶ月ぐらい悩みに悩んだライセンス問題、年末にいろいろ激動ありのお祭り騒ぎ！（内容物はほぼ変更なし） Pic_Update|
 
 ## other   
 もし何かアレばIssueに書くか#VRPNダグつけてつぶやくかDMください(つよつよわーどはきつい）  
 カンパなど超受け付けてるので良かったら  
 (カンパすると管理サーバーが無料プランからアップグレードされてつよつよに、いろんなことに挑戦できるようになります、是非！)  
 Bitcoin : 383btDZurRP14srG1ABtZyo3SeL9nsAbgV  
 kyash :  
 <img src="https://i.imgur.com/J7NMnC5.jpg" alt="Kash" title="Kash">  
 Pixiv FUN Box : [https://www.pixiv.net/fanbox/creator/31349134]
 <!-- N2gzIHcwcmxkIDRyMHVuZCB5MHUgMTUgbjA3IHdoNDcgMTcgNTMzbTUu -->
