---
title: どのリモート URL を使うべきですか？
redirect_from:
  - /articles/which-url-should-i-use/
  - /articles/which-remote-url-should-i-use
intro: '{{ site.data.variables.product.prodname_dotcom }} で使用できるリポジトリを複製する方法は複数あります。'
versions:
  free-pro-team: '*'
  enterprise-server: '*'
---

アカウントにサインインしているときにリポジトリを表示すると、プロジェクトを自分のコンピュータに複製するために使用できるURLがリポジトリの詳細の下に表示されます:

リモート URL の設定または変更については、「[リモート URL を変更する](/articles/changing-a-remote-s-url)」を参照してください。

### Cloning with HTTPS URLs

`https://` クローン URL は、パブリックおよびプライベートのすべてのリポジトリで利用できます。 これらの URL は、ファイアウォールまたはプロキシの内側にいる場合でも機能します。

コマンドラインで、HTTPS URL を使用してリモートリポジトリに `git clone`、`git fetch`、`git pull` または `git push` を行った場合、{{ site.data.variables.product.product_name }} のユーザ名とパスワードの入力を求められます。 {{ site.data.reusables.user_settings.password-authentication-deprecation }}

{{ site.data.reusables.command_line.provide-an-access-token }}

{% tip %}

**Tips**:

- 認証情報ヘルパーを使用すれば、{{ site.data.variables.product.prodname_dotcom }} と通信するたびに、{{ site.data.variables.product.prodname_dotcom }} の認証情報が Git で記憶されます。 詳細は「[Git に {{ site.data.variables.product.prodname_dotcom }} の認証情報をキャッシュする](/github/using-git/caching-your-github-credentials-in-git)」を参照してください。

- コマンドラインで {{ site.data.variables.product.product_name }} の認証なしでリポジトリを複製するために、クローンの代わりに、{{ site.data.variables.product.prodname_desktop }} を使用することができます。 詳しい情報については、「[{{ site.data.variables.product.prodname_dotcom }} から {{ site.data.variables.product.prodname_dotcom }} Desktop にリポジトリをクローンする](/desktop/contributing-to-projects/cloning-a-repository-from-github-to-github-desktop)」を参照してください。

{% endtip %}

 {% if currentVersion == "free-pro-team@latest" %}SSH を使用したくてもポート 22 で接続できない場合は、HTTPS ポートを介する SSH を使用できる場合があります。 詳細は、「[HTTPS ポートを介して SSH を使用する](/github/authenticating-to-github/using-ssh-over-the-https-port)」を参照してください。{% endif %}

### SSH URL を使ってクローンする

SSH URL は、SSH (安全なプロトコル) を介した Git リポジトリへのアクセスを提供します。 これらの URL を使用するには、コンピュータで SSH キーペアを生成し、**公開**鍵を {{ site.data.variables.product.product_name }} アカウントに追加する必要があります。 詳しい情報については「[{{ site.data.variables.product.prodname_dotcom }} に SSH で接続する](/github/authenticating-to-github/connecting-to-github-with-ssh)」を参照してください。

SSH URL を使用して、`git clone`、`git fetch`、`git pull` または `git push` をリモートリポジトリに実行すると、パスワードの入力を求められ、SSH キーパスフレーズを入力する必要があります。 詳しい情報については[SSH キーのパスフレーズを使う](/github/authenticating-to-github/working-with-ssh-key-passphrases)を参照してください。

{% if currentVersion == "free-pro-team@latest" %}SAML シングルサインオン (SSO) を使っている Organization にアクセスしている場合は、認証を受ける前に、Organization にアクセスする SSHキーを認可する必要があります。 詳しい情報については「[SAMLシングルサインオンでの認証について](/github/authenticating-to-github/about-authentication-with-saml-single-sign-on)」および「[SAML シングルサインオンで使うためにSSHキーを認可する](/github/authenticating-to-github/authorizing-an-ssh-key-for-use-with-saml-single-sign-on)」を参照してください。{% endif %}

{% tip %}

**ヒント**: SSH URL は、お使いのコンピュータにリポジトリを作成する際にも、または本番サーバーにコードをデプロイする安全な方法としても使用できます。 デプロイスクリプトで SSH エージェント転送を使用して、サーバー上のキーの管理を回避することもできます。 詳細は「[SSH エージェント転送を使用する](/v3/guides/using-ssh-agent-forwarding/)」を参照してください。

{% endtip %}

{% if currentVersion == "free-pro-team@latest" or currentVersion ver_gt "enterprise-server@2.19" %}

### Cloning with {{ site.data.variables.product.prodname_cli }}

You can also install {{ site.data.variables.product.prodname_cli }} to use {{ site.data.variables.product.product_name }} workflows in your terminal. For more information, the [{{ site.data.variables.product.prodname_cli }}](https://cli.github.com/manual/) documentation.

{% endif %}

### Subversion を使って複製する

[Subversion](https://subversion.apache.org/) クライアントを使用して、{{ site.data.variables.product.prodname_dotcom }} のリポジトリにアクセスすることもできます。 Subversion と Git では、提供する機能群に違いがあります。 詳しい情報については、「[Subversion と Git の違い](/github/importing-your-projects-to-github/what-are-the-differences-between-subversion-and-git)」を参照してください。

Subversion クライアントから {{ site.data.variables.product.prodname_dotcom }} のリポジトリにアクセスすることもできます。 詳細は、「[Subversion クライアントのサポート](/github/importing-your-projects-to-github/support-for-subversion-clients)」を参照してください。

### 参考リンク

- _Pro Git_ ブックのサイトの「[リモートでの作業](https://git-scm.com/book/en/Git-Basics-Working-with-Remotes)」