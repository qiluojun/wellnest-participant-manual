---
layout: default
title: 権限を許可する
parent: 日本語 Android マニュアル
nav_order: 3
permalink: /ja/android/permissions/
---

# 権限を許可する

**WellNest** を初めて開くと、**権限設定ページ**が表示されます。画面の案内に従い、各権限を順番に許可してください。

![Screenshot: Red exclamation mark beside the Permissions icon]({{ '/assets/image_jp/permissions-alert-main-screen.png' | relative_url }})

## 基本的な流れ

1. ページ上の各項目をタップします。
2. アプリと Android システムの案内に従います。
3. 必要な項目がすべて完了するまで続けます。

![Screenshot: Permission configuration page]({{ '/assets/image_jp/permission-configuration-page.png' | relative_url }})

## 通知設定 {#notification-settings}

WellNest はアンケートが回答可能になったときにリマインダーを送信するため、通知の許可は特に重要です。

通常、1 日に 2 回アンケートのリマインダーが届きます。

- Morning Survey のリマインダー
- Evening Survey のリマインダー

Android から通知の許可を求められたら、アプリからの通知を許可してください。

![Screenshot: Notification permission prompt]({{ '/assets/image_jp/notification-permission-prompt.png' | relative_url }})

アプリから通知設定を開くよう案内された場合は、WellNest の通知カテゴリが有効になっていることを確認してください。

![Screenshot: Android notification categories for WellNest]({{ '/assets/image_jp/notification-settings-open.png' | relative_url }})

![Screenshot]({{ '/assets/image_jp/other1.png' | relative_url }})
![Screenshot]({{ '/assets/image_jp/other2.png' | relative_url }})

![Screenshot: Android notification categories for WellNest]({{ '/assets/image_jp/android-notification-categories.png' | relative_url }})

以下の通知カテゴリが有効になっていることを確認してください。

- App Close Warning
- Survey Reminders (Scheduled)
- Survey Reminders

![Screenshot]({{ '/assets/image_jp/app-close-warning-category.png' | relative_url }})
![Screenshot]({{ '/assets/image_jp/app-close-warning-default.png' | relative_url }})

おやすみモードなどを使用している場合は、アンケートの回答時間を逃さないよう、アンケートリマインダーがおやすみモード中でも通知される設定にすることをおすすめします。

![Screenshot: Override Do Not Disturb setting]({{ '/assets/image_jp/override-do-not-disturb.png' | relative_url }})

![Screenshot: Survey reminder notification categories]({{ '/assets/image_jp/survey-reminder-notification-categories.png' | relative_url }})

## その他の権限項目

**通知設定**が完了したら、**Past Health Data** に進む前に、権限設定ページに表示されている次の項目を順番に進めてください。第 3 項目から第 6 項目については、画面の指示に従って操作してください。基本的な流れは、**許可**ボタンをタップし、その後に表示される Android システムのポップアップで対応する権限を許可することです。

NOTE: 位置情報は、個々人よって異なる基点からの相対座標のみが記録され、絶対的な位置情報（つまり、緯度・経度）は記録されません。基点情報は、このデバイスのみに保存されています。
{: .privacy-note }

## Past Health Data

最後の項目では、**WellNest Health** が自動的に開きます。WellNest Health に表示される案内に従い、その部分の設定を完了してください。

![Screenshot: WellNest Health initial screen]({{ '/assets/images/wellnest-health-initial-screen.png' | relative_url }})

画面の案内に従い、補助アプリに表示されるアップロードまたは権限許可のボタンをタップしてください。

補助アプリで成功状態が表示されたら、WellNest に戻ります。その後、権限設定ページを閉じてかまいません。

![Screenshot: Past Health Data permission step]({{ '/assets/image_jp/past-health-data-permission.png' | relative_url }})

## 権限設定が完了したか確認する方法 {#how-to-confirm-permissions-are-complete}

WellNest の Permissions アイコン横にある赤い感嘆符が消えていれば、権限設定は完了しています。

![Screenshot: Permission status not finished]({{ '/assets/image_jp/main-app-permission-status-not-finished.png' | relative_url }})

![Screenshot: Permission status finished]({{ '/assets/image_jp/main-app-permission-status-finished.png' | relative_url }})

赤い感嘆符がまだ表示されている場合:

1. **権限設定ページ**に戻ります。
2. 未完了の項目を確認します。
3. 未完了の項目をタップし、もう一度試してください。

## WellNest Health はいつアンインストールできますか？ {#when-can-i-uninstall-wellnest-health}

**WellNest Health** は、以下の両方が完了した後にのみアンインストールできます。

- WellNest で権限設定を完了している。
- Permissions アイコン横の赤い感嘆符が消えている。

それより前に WellNest Health をアンインストールしないでください。早すぎるタイミングでアンインストールすると、権限設定が完了しない可能性があります。

## 次へ
{: .next-step-heading }

権限設定が完了したら、[アンケート]({{ '/ja/android/surveys/' | relative_url }})、特に[事前アンケート]({{ '/ja/android/surveys/#pre-study-survey' | relative_url }})へ進んでください。
{: .next-step }
