---
title: Microsoft Entra が Copilot for Security に新しい ID スキルを追加
date: 2024-04-07 11:00
tags:
  - Azure AD
  - US Identity Blog
---

# Microsoft Entra が Copilot for Security に新しい ID スキルを追加

こんにちは、Azure Identity サポート チームの 名取 です。

本記事は、2024 年 3 月 13 日に米国の Microsoft Entra Blog で公開された [Microsoft Entra adds identity skills to Copilot for Security](https://techcommunity.microsoft.com/t5/microsoft-entra-blog/microsoft-entra-adds-identity-skills-to-copilot-for-security/ba-p/4081857) を意訳したものになります。ご不明点等ございましたらサポート チームまでお問い合わせください。

----

本日、Microsoft Copilot for Security が 4 月 1 日より全世界で一般提供されることを[発表しました](https://www.microsoft.com/en-us/security/blog/2024/03/13/microsoft-copilot-for-security-is-generally-available-on-april-1-2024-with-new-capabilities/)。 スタンドアロンの Copilot for Security では、次の新しい Microsoft Entra のスキルが使用できるようになります: 「ユーザーの詳細」、「グループの詳細」、「サインイン ログ」、「監査ログ」、「診断ログ」です。Microsoft Entra に組み込まれたスキルである「ユーザーリスク調査」も、パブリックプレビューで利用できるようになります。 

これらの新しい機能により、ID の観点とセキュリティ インシデントに関する知見が得られるようになり、ID 関連のリスクとサインイン問題の解決を支援することで、ID 管理者が侵害からよりよく保護されるようなります。Copilot for Security に新しい ID 機能を導入することで、ID およびセキュリティ管理者を [人並外れたスピードで保護](https://www.microsoft.com/ja-jp/security/business/ai-machine-learning/microsoft-copilot-security)し、支援できることを嬉しく思います。 

## Copilot for Security の新しい ID スキル

次に、Copilot for Security のこれらの新しい Entra のスキルを管理者が自然言語のプロンプトを介して日常の業務にどのように生かせるか、また、どのように ID 管理者がアクセスを保護していけるか順に詳しく見てみましょう。

**ユーザー詳細** では、ユーザー名、所在地、役職、連絡先、認証方法、アカウント作成日、アカウントの状態など、Entra で管理されているユーザーの関連情報をすばやく確認できます。管理者は、Copilot に「このユーザーについて詳しく教えてください」、「過去 5 日間に作成されたアクティブなユーザーをリストアップしてください」、「このユーザーにはどのような認証方法が登録されていますか」、「このユーザーのアカウントは有効な状態ですか」といったフレーズを入力することで、質問への答えを瞬時に引き出すことができます。

**グループの詳細** では、Entra で管理されているあらゆるグループの詳細をつかむことができます。 管理者は、Copilot に「グループ X の所有者は誰ですか」、「XYZ で始まるグループについて教えてください」、「このグループには何人のメンバーがいますか」といった質問をして、すぐに状況を把握することができます。
 
**サインイン ログ** では、サインイン ログに加えて、テナントに適用されてい条件付きアクセス ポリシーに関する情報を中心に、ID 観点の調査とトラブルシューティングを支援します。管理者は、「このユーザーの最近のサインインを表示して」、「この IP アドレスからのサインインを表示して」、または「このユーザーの失敗したサインインを表示して」など Copilot に依頼するだけです。

**監査ログ** は、ロールやアクセス権限の変更など、監査ログに関連する異常を特定するのに役立ちます。管理者は、「このユーザーが開始したアクションの監査ログを表示して」または「これに似たイベントの監査ログを表示して」と Copilot に依頼するだけです。
  
ここでは例として、ID 管理者が、ユーザー名「rashok」という危険なユーザーを特定した上で、Copilot に「rashok」の 3 月 5 日の監査ログを説明するよう要求し、そのユーザーの侵害のリスクが高かった期間中にどのような行動がとられたかを調べています。
  
![ID 管理者が rashok というユーザー名にリスクがあると気づき、Copilot に 3 月 5 日の監査ログに関し、rashok の侵害のリスクが高まっていた際にどのような操作を行ったかを確認しています。](./microsoft-entra-adds-identity-skills-to-copilot-for-security/fig1.jpeg)

> (上図翻訳)  
> 2024 年 3 月 5 日、Ravi Ashok (ユーザー ID: d7972ccc- 82b3-4ea5-a3b4-7902de3f986c) という名前のユーザーによって、Entra ID 監査ログに関連する一連のアクティビティが開始されました。すべてのアクティビティが成功しました。主なアクティビティの概要は以下のとおりです:
>
> **1. ユーザーがアクセス パッケージの割り当てを要求**: この操作は 23:48:07.20892257 に実行されました。ターゲット リソースは、ID が "90425fa0-9141-4930- 92d0-7d6808959d65" の AccessPackageAssignmentRequest でした。リクエストの状態は「Submitted」に更新され、さらにリクエストの状態が「Accepted」に更新されました。
> 
> **2. アクセス パッケージ割り当てリクエストの自動承認**: この操作は 23:48:11.1376478Z に実行されました。ターゲット リソースは、ID が "90425fa0-9141-4930-92d0-7d6808959d65" の AccessPackageAssignmentRequest でした。リクエストの状態が「Delivering」に更新され、さらにリクエストの状態が「AutoApproved」に更新されました。
> 
> **3. アクセス パッケージ のリソース割り当ての完了**: この操作は 23:48:15.0048206Z に実行されました。ターゲット リソース タイプは「Other」で、ID は "af8e1455-b4c5-430d-868f-aa4e76258518" でした。ステータスが「Fulfilled」に更新されました。

**診断ログ** は、テナントのポリシー設定が健全および完全でるかを確認するのに役立ちます。これにより、サインインログと監査ログが正しく設定され、ログ収集プロセスに抜け漏れがないことを確認できます。管理者は「テナントではどのようなログが収集されているか」または「監査ログは有効になっているか」を尋ねて、抜け漏れがあれば迅速に修正できます。

Copilot for Security のこれら新しい Entra のスキルについては [こちらの資料](https://learn.microsoft.com/ja-jp/entra/fundamentals/copilot-security-entra) をご覧ください。

## Entra における Copilot を使用したリスク調査
  
Copilot for Security によって ID のリスクへの対応速度がどれだけ向上するかをよりよく理解するために、数回の異常なサインイン試行により、あるユーザーに高リスク レベルのフラグが立てられたシナリオを考えてみたいと思います。Copilot for Security のパブリック プレビュー機能である Microsoft Entra のユーザー リスク調査スキルを使用することで、管理者はユーザーのリスク レベルを分析すると共に、インシデントの影響を緩和して状況を解決する方法について推奨事項をえることができます:
  
![ID 管理者が、あるユーザーが異常なサインインにより高リスクにあると気づきました。Copilot for Security により、管理者は問題のユーザーをクリックすることで、リスクの詳細を速やかに確認すると共に、復旧に向けた手順を確認することで、調査と解決を迅速に行うことができます。](./microsoft-entra-adds-identity-skills-to-copilot-for-security/movie1.gif) 
  
ID 管理者が、一連の異常なサインインにより、ユーザーが高リスクであるとマークされたことに気づいたとします。Copilot for Security を使用すると、管理者は問題のユーザーをクリックしてリスクの概要と修復手順を即座に受け取ることができ、リスクを迅速に調査して解決に導くことが可能となります。
  
Copilot は、ユーザのリスクレベルが上昇した理由を自然言語で要約します。次に、Copilot は、リスクを無効化して事象を解決するための実行可能な手順のリストを提供します。最後に、Copilot は、侵害された ID による影響を最小化するため、ID 管理者が ID の脅威への対応を自動化するにあたっての推奨事項を提示します。

Microsoft Entra のユーザーリスクの調査スキルについては [こちらの資料](https://learn.microsoft.com/ja-jp/entra/fundamentals/copilot-entra-risky-user-summarization) をご確認ください。

## Copilot for Security を使用する方法
  
当社は、従量課金のライセンス モデルを導入しており、Copilot for Security は、市場のどのソリューションよりも幅広い組織で利用できるようになっています。この柔軟で従量課金ベースの価格設定モデルにより、お客様はすぐに利用を開始することができ、その後、ニーズと予算に応じて使用量とコストを調整いただけます。Copilot for Security は、2024 年 4 月 1 日からご購入いただけます。今すぐ担当者に相談し、素晴らしいメリットをいち早く実感していただけたらと存じます。
  
Copilot for Security により、セキュリティ チームと IT チームはいち早く AI の時代に移行し、スキルセットを強化できるようになります。これは、生成 AI ツールでお客様の組織を強化するための大きなマイルストーンであり、弊社があらゆる人とあらゆるモノへの ID とアクセスをよりよく保護するためのに、お客様やパートナー様とともに取り組めることを大変誇りに思います。

Sarah Scott,  
Principal Manager, Product Management
  
