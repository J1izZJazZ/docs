---
title: 2 要素認証と SAML シングルサインオンについて
intro: Organization の管理者は、SAML シングルサインオンと 2 要素認証を共に有効化し、Organization のメンバーの認証方法を追加できます。
product: '{{ site.data.reusables.gated-features.saml-sso }}'
redirect_from:
  - /articles/about-two-factor-authentication-and-saml-single-sign-on
versions:
  free-pro-team: '*'
---

2 要素認証 (2FA) は、Organization のメンバーに基本的な認証を提供します。 2FA を有効化することで、Organization の管理者はメンバーの {{ site.data.variables.product.product_name }} アカウントが悪用される可能性を抑制できます。 2FA に関する詳細は「[2 要素認証について](/articles/about-two-factor-authentication)」を参照してください。

認証方法を追加するために、Organization の管理者は [SAML シングルサインオン (SSO) を有効化](/articles/enabling-and-testing-saml-single-sign-on-for-your-organization)し、Organization のメンバーが Organization へのアクセスにシングルサインオンを使わなければならないようにすることができます。 詳細は「[SAML シングルサインオンを使うアイデンティティおよびアクセス管理について](/articles/about-identity-and-access-management-with-saml-single-sign-on)」を参照してください。

2 要素認証と SAML SSO をどちらも有効化した場合、Organization のメンバーは以下のようにしなければなりません:
- {{ site.data.variables.product.product_name }} アカウントへのログインには 2 要素認証を利用
- Organization へのアクセスにはシングルサインオンを利用
- API あるいは Git のアクセスには認可されたトークンを使い、トークンの認可にはシングルサインオンを利用

### 参考リンク

- [Organization 用の SAML シングルサインオンの強制](/articles/enforcing-saml-single-sign-on-for-your-organization)