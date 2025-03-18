<!DOCTYPE html>
<!-- saved from url=(0066)https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md -->
<html class="gl-light ui-neutral with-top-bar with-header " lang="fr" style="--broadcast-message-height: 0px;"><head prefix="og: http://ogp.me/ns#"><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<meta content="IE=edge" http-equiv="X-UA-Compatible">
<meta content="width=device-width, initial-scale=1" name="viewport">
<title>tp/1/part4.md · main · it4 / b2e-cloud-2024 · GitLab</title>
<script nonce="">
//<![CDATA[
window.gon={};gon.api_version="v4";gon.default_avatar_url="https://gitlab.com/assets/no_avatar-849f9c04a3a0d0cea2424ae97b27447dc64a7dbfae83c036c45b403392f0e8ba.png";gon.max_file_size=100;gon.asset_host=null;gon.webpack_public_path="/assets/webpack/";gon.relative_url_root="";gon.user_color_mode="gl-light";gon.user_color_scheme="white";gon.markdown_surround_selection=null;gon.markdown_automatic_lists=null;gon.math_rendering_limits_enabled=true;gon.analytics_url="https://collector.prd-278964.gl-product-analytics.com";gon.analytics_id="715db59f-f350-4bfd-aef8-e7a7f0c023f0";gon.sentry_dsn="https://f5573e26de8f4293b285e556c35dfd6e@new-sentry.gitlab.net/4";gon.sentry_environment="gprd";gon.sentry_clientside_traces_sample_rate=0.05;gon.recaptcha_api_server_url="https://www.recaptcha.net/recaptcha/api.js";gon.recaptcha_sitekey="6LfAERQTAAAAAL4GYSiAMGLbcLyUIBSfPrDNJgeC";gon.gitlab_url="https://gitlab.com";gon.promo_url="https://about.gitlab.com";gon.forum_url="https://forum.gitlab.com";gon.docs_url="https://docs.gitlab.com";gon.revision="01ed5d73d7f";gon.feature_category="source_code_management";gon.gitlab_logo="/assets/gitlab_logo-2957169c8ef64c58616a1ac3f4fc626e8a35ce4eb3ed31bb0d873712f2a041a0.png";gon.secure=true;gon.sprite_icons="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg";gon.sprite_file_icons="/assets/file_icons/file_icons-59d148c7ea628b0ec3975493002fa45de1d4d8c15b2bf59775965ab9d67d62ab.svg";gon.emoji_sprites_css_path="/assets/emoji_sprites-bd26211944b9d072037ec97cb138f1a52cd03ef185cd38b8d1fcc963245199a1.css";gon.emoji_backend_version=4;gon.gridstack_css_path="/assets/lazy_bundles/gridstack-4cd1da7c8adb8553e78a4f5545a8ab57a46258e091e6ac0382e6de79bca5ea3c.css";gon.test_env=false;gon.disable_animations=null;gon.suggested_label_colors={"#cc338b":"Magenta-pink","#dc143c":"Crimson","#c21e56":"Rose red","#cd5b45":"Dark coral","#ed9121":"Carrot orange","#eee600":"Titanium yellow","#009966":"Green-cyan","#8fbc8f":"Dark sea green","#6699cc":"Blue-gray","#e6e6fa":"Lavender","#9400d3":"Dark violet","#330066":"Deep violet","#36454f":"Charcoal grey","#808080":"Gray"};gon.first_day_of_week=0;gon.time_display_relative=true;gon.time_display_format=0;gon.ee=true;gon.jh=false;gon.dot_com=true;gon.uf_error_prefix="UF";gon.pat_prefix="glpat-";gon.keyboard_shortcuts_enabled=true;gon.diagramsnet_url="https://embed.diagrams.net";gon.features={"vscodeWebIde":true,"uiForOrganizations":false,"organizationSwitching":false,"findAndReplace":false,"removeMonitorMetrics":true,"workItemsViewPreference":true,"searchButtonTopRight":false,"mergeRequestDashboard":true,"newProjectCreationForm":false,"workItemsClientSideBoards":false,"duoChatDynamicDimension":true,"duoChatMultiThread":false,"advancedContextResolver":true,"vulnerabilityReportTypeScannerFilter":true,"inlineBlame":false,"blobRepositoryVueHeaderApp":true,"blobOverflowMenu":false,"filterBlobPath":false,"directoryCodeDropdownUpdates":false};gon.roadmap_epics_limit=1000;gon.subscriptions_url="https://customers.gitlab.com";gon.subscriptions_legacy_sign_in_url="https://customers.gitlab.com/customers/sign_in?legacy=true";gon.billing_accounts_url="https://customers.gitlab.com/billing_accounts";gon.payment_form_url="https://customers.gitlab.com/payment_forms/cc_validation";gon.payment_validation_form_id="payment_method_validation";gon.licensed_features={"remoteDevelopment":true};
//]]>
</script>


<script nonce="">
//<![CDATA[
var gl = window.gl || {};
gl.startup_calls = {"/it4lik/b2e-cloud-2024/-/refs/main/logs_tree/tp/1?format=json\u0026offset=0":{},"/it4lik/b2e-cloud-2024/-/blob/main/README.md?format=json\u0026viewer=rich":{}};
gl.startup_graphql_calls = [{"query":"query pathLastCommit($projectPath: ID!, $path: String, $ref: String!, $refType: RefType) {\n  project(fullPath: $projectPath) {\n    __typename\n    id\n    repository {\n      __typename\n      paginatedTree(path: $path, ref: $ref, refType: $refType) {\n        __typename\n        nodes {\n          __typename\n          lastCommit {\n            __typename\n            id\n            sha\n            title\n            titleHtml\n            descriptionHtml\n            message\n            webPath\n            authoredDate\n            authorName\n            authorGravatar\n            author {\n              __typename\n              id\n              name\n              avatarUrl\n              webPath\n            }\n            signature {\n              __typename\n              ... on GpgSignature {\n                gpgKeyPrimaryKeyid\n                verificationStatus\n              }\n              ... on X509Signature {\n                verificationStatus\n                x509Certificate {\n                  id\n                  subject\n                  subjectKeyIdentifier\n                  x509Issuer {\n                    id\n                    subject\n                    subjectKeyIdentifier\n                  }\n                }\n              }\n              ... on SshSignature {\n                verificationStatus\n                keyFingerprintSha256\n              }\n            }\n            pipelines(ref: $ref, first: 1) {\n              __typename\n              edges {\n                __typename\n                node {\n                  __typename\n                  id\n                  detailedStatus {\n                    __typename\n                    id\n                    detailsPath\n                    icon\n                    tooltip\n                    text\n                    group\n                  }\n                }\n              }\n            }\n          }\n        }\n      }\n    }\n  }\n}\n","variables":{"projectPath":"it4lik/b2e-cloud-2024","ref":"main","path":"tp/1","refType":null}},{"query":"query getPermissions($projectPath: ID!) {\n  project(fullPath: $projectPath) {\n    id\n    __typename\n    userPermissions {\n      __typename\n      pushCode\n      forkProject\n      createMergeRequestIn\n    }\n  }\n}\n","variables":{"projectPath":"it4lik/b2e-cloud-2024"}},{"query":"fragment PageInfo on PageInfo {\n  __typename\n  hasNextPage\n  hasPreviousPage\n  startCursor\n  endCursor\n}\n\nfragment TreeEntry on Entry {\n  __typename\n  id\n  sha\n  name\n  flatPath\n  type\n}\n\nquery getFiles(\n  $projectPath: ID!\n  $path: String\n  $ref: String!\n  $refType: RefType\n  $pageSize: Int!\n  $nextPageCursor: String\n) {\n  project(fullPath: $projectPath) {\n    id\n    __typename\n    repository {\n      __typename\n      tree(path: $path, ref: $ref, refType: $refType) {\n        __typename\n        trees(first: $pageSize, after: $nextPageCursor) {\n          __typename\n          edges {\n            __typename\n            node {\n              ...TreeEntry\n              webPath\n            }\n          }\n          pageInfo {\n            ...PageInfo\n          }\n        }\n        submodules(first: $pageSize, after: $nextPageCursor) {\n          __typename\n          edges {\n            __typename\n            node {\n              ...TreeEntry\n              webUrl\n              treeUrl\n            }\n          }\n          pageInfo {\n            ...PageInfo\n          }\n        }\n        blobs(first: $pageSize, after: $nextPageCursor) {\n          __typename\n          edges {\n            __typename\n            node {\n              ...TreeEntry\n              mode\n              webPath\n              lfsOid\n            }\n          }\n          pageInfo {\n            ...PageInfo\n          }\n        }\n      }\n    }\n  }\n}\n","variables":{"nextPageCursor":"","pageSize":100,"projectPath":"it4lik/b2e-cloud-2024","ref":"main","path":"tp/1","refType":null}}];

if (gl.startup_calls && window.fetch) {
  Object.keys(gl.startup_calls).forEach(apiCall => {
   gl.startup_calls[apiCall] = {
      fetchCall: fetch(apiCall, {
        // Emulate XHR for Rails AJAX request checks
        headers: {
          'X-Requested-With': 'XMLHttpRequest'
        },
        // fetch won’t send cookies in older browsers, unless you set the credentials init option.
        // We set to `same-origin` which is default value in modern browsers.
        // See https://github.com/whatwg/fetch/pull/585 for more information.
        credentials: 'same-origin'
      })
    };
  });
}
if (gl.startup_graphql_calls && window.fetch) {
  const headers = {"X-CSRF-Token":"W64VxIeRVawFqBREKKB2HaxFqwOddFfJqNb4rRMPt41mcqvVTtSYn-CBa9BK_mpNFb0W63E2hux4i6TmIz0fHg","x-gitlab-feature-category":"source_code_management"};
  const url = `https://gitlab.com/api/graphql`

  const opts = {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      ...headers,
    }
  };

  gl.startup_graphql_calls = gl.startup_graphql_calls.map(call => ({
    ...call,
    fetchCall: fetch(url, {
      ...opts,
      credentials: 'same-origin',
      body: JSON.stringify(call)
    })
  }))
}


//]]>
</script>



<link rel="stylesheet" href="./TP1_files/application-66bf9396f3145d208c2e25101e02632a67c4e76b46c65f4c9a523ab6bb8a2122.css">
<link rel="stylesheet" href="./TP1_files/tree-36265195585af5e9c554d953e140f9c837af2e2eecb061d3f93d2857768eb286.css"><link rel="stylesheet" href="./TP1_files/commit_description-1e2cba4dda3c7b30dd84924809020c569f1308dea51520fe1dd5d4ce31403195.css"><link rel="stylesheet" href="./TP1_files/projects-80846bc4bdd46036586f0a20fdc1d14b080c3cabfcebf1f71b5e1cb019f70b56.css"><link rel="stylesheet" href="./TP1_files/work_items-f8b0433a074a1464d564be96c61f98abba72c32c594f4624f237b4e41b1a5679.css"><link rel="stylesheet" href="./TP1_files/notes_shared-8b38073ba71abd72b511b161ac1c0567ac634b689428f7c74591325093229970.css">
<link rel="stylesheet" href="./TP1_files/application_utilities-7844decc020ce5472253adae1ee2b329cdb6ddd08043b91daa3c9ed5530f5142.css">
<link rel="stylesheet" href="./TP1_files/tailwind-fe07826105549e62462d761509d4be7d46f7837bdf8ec2fb3e1a281f2018acaf.css">


<link rel="stylesheet" href="./TP1_files/fonts-fae5d3f79948bd85f18b6513a025f863b19636e85b09a1492907eb4b1bb0557b.css">
<link rel="stylesheet" href="./TP1_files/white-99cce4f4b362f6840d7134d4129668929fde49c4da11d6ebf17f99768adbd868.css">

<script src="./TP1_files/runtime.c894c003.bundle.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/main.9ae3190e.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/tracker.e580a369.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/analytics.3d11ffb4.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script nonce="">
//<![CDATA[
window.snowplowOptions = {"namespace":"gl","hostname":"snowplowprd.trx.gitlab.net","cookieDomain":".gitlab.com","appId":"gitlab","formTracking":true,"linkClickTracking":true}

gl = window.gl || {};
gl.snowplowStandardContext = {"schema":"iglu:com.gitlab/gitlab_standard/jsonschema/1-1-1","data":{"environment":"production","source":"gitlab-rails","correlation_id":"01JPKC6S0MAYDZGR4Y1BQDY7C9","plan":"free","extra":{},"user_id":null,"global_user_id":null,"is_gitlab_team_member":null,"namespace_id":1167495,"project_id":68004674,"feature_enabled_by_namespace_ids":null,"realm":"saas","instance_id":"ea8bf810-1d6f-4a6a-b4fd-93e8cbd8b57f","host_name":"gitlab-webservice-web-5d94c9f777-f9nks","instance_version":"17.10.0","context_generated_at":"2025-03-18T00:59:38.061Z"}}
gl.snowplowPseudonymizedPageUrl = "https://gitlab.com/namespace1167495/project68004674/-/tree/main/tp/1";
gl.maskedDefaultReferrerUrl = "https://gitlab.com/namespace/project/-/blob/id";
gl.ga4MeasurementId = 'G-ENFH3X7M5Y';


//]]>
</script>
<link rel="preload" href="./TP1_files/application_utilities-7844decc020ce5472253adae1ee2b329cdb6ddd08043b91daa3c9ed5530f5142.css" as="style" type="text/css" nonce="">
<link rel="preload" href="./TP1_files/application-66bf9396f3145d208c2e25101e02632a67c4e76b46c65f4c9a523ab6bb8a2122.css" as="style" type="text/css" nonce="">
<link rel="preload" href="./TP1_files/white-99cce4f4b362f6840d7134d4129668929fde49c4da11d6ebf17f99768adbd868.css" as="style" type="text/css" nonce="">
<link crossorigin="" href="https://snowplowprd.trx.gitlab.net/" rel="preconnect">
<link as="font" crossorigin="" href="https://gitlab.com/assets/gitlab-sans/GitLabSans-1e0a5107ea3bbd4be93e8ad2c503467e43166cd37e4293570b490e0812ede98b.woff2" rel="preload">
<link as="font" crossorigin="" href="https://gitlab.com/assets/gitlab-sans/GitLabSans-Italic-38eaf1a569a54ab28c58b92a4a8de3afb96b6ebc250cf372003a7b38151848cc.woff2" rel="preload">
<link as="font" crossorigin="" href="https://gitlab.com/assets/gitlab-mono/GitLabMono-08d2c5e8ff8fd3d2d6ec55bc7713380f8981c35f9d2df14e12b835464d6e8f23.woff2" rel="preload">
<link as="font" crossorigin="" href="https://gitlab.com/assets/gitlab-mono/GitLabMono-Italic-38e58d8df29485a20c550da1d0111e2c2169f6dcbcf894f2cd3afbdd97bcc588.woff2" rel="preload">
<link rel="preload" href="./TP1_files/fonts-fae5d3f79948bd85f18b6513a025f863b19636e85b09a1492907eb4b1bb0557b.css" as="style" type="text/css" nonce="">

<script src="./TP1_files/app-912f95d9f377e7902375327e7dd90e88aa746afce6fd4b11ae6aaa64cb712880.js.téléchargement" defer="defer" nonce=""></script>

<script src="./TP1_files/sentry.6d017742.chunk.js.téléchargement" defer="defer" nonce=""></script>

<script src="./TP1_files/commons-pages.groups.analytics.dashboards-pages.groups.harbor.repositories-pages.groups.iteration_ca-f757bfc9.f1145b14.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.groups.new-pages.import.gitlab_projects.new-pages.import.manifest.new-pages.projects.n-44c6c18e.d69cc974.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.search.show-super_sidebar.c2d9c3cd.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/super_sidebar.c1ce2f51.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.projects-pages.projects.activity-pages.projects.alert_management.details-pages.project-68d77824.c8626966.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.groups.packages-pages.groups.registry.repositories-pages.groups.security.policies.edit-429ebfda.daa705c1.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/16.18f3aa66.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/90.ba8159a9.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/105.814705a3.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/130.ccd5e6b8.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.projects.blob.show-pages.projects.show-pages.projects.snippets.show-pages.projects.tre-c684fcf6.39941726.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.projects.blob.edit-pages.projects.blob.new-pages.projects.blob.show-pages.projects.sho-ec79e51c.da06f602.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.groups.show-pages.projects.blob.show-pages.projects.show-pages.projects.tree.show.8ee71ea6.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.projects.blob.show-pages.projects.security.vulnerabilities.show-pages.projects.show-pa-5ff3b950.f0404dc1.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.projects.blob.show-pages.projects.show-pages.projects.tree.show.0b96768c.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/commons-pages.projects.blob.show-pages.projects.tree.show-treeList.14ec2ceb.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/treeList.3c7f4026.chunk.js.téléchargement" defer="defer" nonce=""></script>
<script src="./TP1_files/pages.projects.tree.show.0387947d.chunk.js.téléchargement" defer="defer" nonce=""></script>

<meta content="object" property="og:type">
<meta content="GitLab" property="og:site_name">
<meta content="tp/1 · main · it4 / b2e-cloud-2024 · GitLab" property="og:title">
<meta content="GitLab.com" property="og:description">
<meta content="https://gitlab.com/assets/twitter_card-570ddb06edf56a2312253c5872489847a0f385112ddbcd71ccfa1570febab5d2.jpg" property="og:image">
<meta content="64" property="og:image:width">
<meta content="64" property="og:image:height">
<meta content="https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main/tp/1" property="og:url">
<meta content="summary" property="twitter:card">
<meta content="tp/1 · main · it4 / b2e-cloud-2024 · GitLab" property="twitter:title">
<meta content="GitLab.com" property="twitter:description">
<meta content="https://gitlab.com/assets/twitter_card-570ddb06edf56a2312253c5872489847a0f385112ddbcd71ccfa1570febab5d2.jpg" property="twitter:image">

<meta name="csrf-param" content="authenticity_token">
<meta name="csrf-token" content="Cmo3RwGonI941EK8KsFQYpEH62mbN5hmOCTVWfyxBa03tolWyO1RvJ39PShIn0wyKP9WgXd1SUPoeYkSzIOtPg">
<meta name="csp-nonce" content="ok9rpN7ZheOppjGSgoMAnA==">
<meta name="action-cable-url" content="/-/cable">
<link href="https://gitlab.com/-/manifest.json" rel="manifest">
<link rel="icon" type="image/png" href="https://gitlab.com/assets/favicon-72a2cad5025aa931d6ea56c3201d1f18e68a8cd39788c7c80d5b2b82aa5143ef.png" id="favicon" data-original-href="/assets/favicon-72a2cad5025aa931d6ea56c3201d1f18e68a8cd39788c7c80d5b2b82aa5143ef.png">
<link rel="apple-touch-icon" type="image/x-icon" href="https://gitlab.com/assets/apple-touch-icon-b049d4bc0dd9626f31db825d61880737befc7835982586d015bded10b4435460.png">
<link href="https://gitlab.com/search/opensearch.xml" rel="search" title="Search GitLab" type="application/opensearchdescription+xml">
<link rel="alternate" type="application/atom+xml" title="b2e-cloud-2024:main commits" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/commits/main?format=atom">




<meta content="GitLab.com" name="description">
<meta content="#ececef" name="theme-color">
<style>
svg[data-v-9534917c] {
  pointer-events: none;

  position: fixed;
  right: 0;
}
svg polygon[data-v-9534917c],
svg rect[data-v-9534917c] {
  pointer-events: auto;
}
</style><style>
.fake-input[data-v-26a01bbc] {
  position: absolute;
  top: 14px;
  left: 39px;
}
</style><style>
.input-box-wrapper[data-v-4807f23d] {
  position: relative;
}
.fake-input-wrapper[data-v-4807f23d] {
  position: absolute;
}
</style><script charset="utf-8" src="./TP1_files/shortcutsBundle.a6bcaaaa.chunk.js.téléchargement"></script><style type="text/css">.resizable-component[data-v-3de5149f]{position:relative}.resizable-component>.resizable-r[data-v-3de5149f]{z-index:90;cursor:e-resize;top:0;height:100%}.resizable-component>.resizable-r[data-v-3de5149f],.resizable-component>.resizable-rb[data-v-3de5149f]{display:block;position:absolute;touch-action:none;user-select:none;-moz-user-select:none;-webkit-user-select:none;width:12px;right:-6px}.resizable-component>.resizable-rb[data-v-3de5149f]{cursor:se-resize;height:12px;bottom:-6px;z-index:91}.resizable-component>.resizable-b[data-v-3de5149f]{z-index:90;cursor:s-resize;width:100%;left:0}.resizable-component>.resizable-b[data-v-3de5149f],.resizable-component>.resizable-lb[data-v-3de5149f]{display:block;position:absolute;touch-action:none;user-select:none;-moz-user-select:none;-webkit-user-select:none;height:12px;bottom:-6px}.resizable-component>.resizable-lb[data-v-3de5149f]{cursor:sw-resize;width:12px;left:-6px;z-index:91}.resizable-component>.resizable-l[data-v-3de5149f]{z-index:90;cursor:w-resize;height:100%;top:0}.resizable-component>.resizable-l[data-v-3de5149f],.resizable-component>.resizable-lt[data-v-3de5149f]{display:block;position:absolute;touch-action:none;user-select:none;-moz-user-select:none;-webkit-user-select:none;width:12px;left:-6px}.resizable-component>.resizable-lt[data-v-3de5149f]{cursor:nw-resize;height:12px;top:-6px;z-index:91}.resizable-component>.resizable-t[data-v-3de5149f]{z-index:90;cursor:n-resize;width:100%;left:0}.resizable-component>.resizable-rt[data-v-3de5149f],.resizable-component>.resizable-t[data-v-3de5149f]{display:block;position:absolute;touch-action:none;user-select:none;-moz-user-select:none;-webkit-user-select:none;height:12px;top:-6px}.resizable-component>.resizable-rt[data-v-3de5149f]{cursor:ne-resize;width:12px;right:-6px;z-index:91}</style><style>
.input-copy-show-disc {
  -webkit-text-security: disc;
}
/*
  Bootstrap's invalid feedback displays based on a sibling selector which is incompatible with form-input-group.
  So we must manually force the feedback to display when the input is invalid. See: https://github.com/bootstrap-vue/bootstrap-vue/issues/1251
 */
.input-copy-toggle-visibility-is-invalid .invalid-feedback {
  display: block;
}
</style><script charset="utf-8" src="./TP1_files/hello.3f1c4b27.chunk.js.téléchargement"></script><style>
/* Temporary override until we have
   * widths available in GlDisclosureDropdown
   * https://gitlab.com/gitlab-org/gitlab-ui/-/issues/2501
   */
.code-dropdown .gl-new-dropdown-panel {
  width: 100%;
  max-width: 348px;
}
</style><style>
/* Temporary override until we have
   * widths available in GlDisclosureDropdown
   * https://gitlab.com/gitlab-org/gitlab-ui/-/issues/2501
   */
.code-dropdown .gl-new-dropdown-panel {
  width: 100%;
  max-width: 348px;
}
</style><style>
/* This is to override a margin caused by bootstrap */
.non-gfm-markdown-block {
p {
    margin-bottom: 0;
}
}
</style><script charset="utf-8" src="./TP1_files/1301.101a592e.chunk.js.téléchargement"></script><script charset="utf-8" src="./TP1_files/initInviteMembersTrigger.a5f97dcc.chunk.js.téléchargement"></script><script charset="utf-8" src="./TP1_files/prosemirror.2c93e8b8.chunk.js.téléchargement"></script><script charset="utf-8" src="./TP1_files/77.fad5ced3.chunk.js.téléchargement"></script><script charset="utf-8" src="./TP1_files/vendors-content_editor-gfm_copy_extra.b3da2b52.chunk.js.téléchargement"></script><script charset="utf-8" src="./TP1_files/vendors-gfm_copy_extra.62350ae7.chunk.js.téléchargement"></script><script charset="utf-8" src="./TP1_files/gfm_copy_extra.c15a184f.chunk.js.téléchargement"></script><style data-tiptap-style="">.ProseMirror {
  position: relative;
}

.ProseMirror {
  word-wrap: break-word;
  white-space: pre-wrap;
  white-space: break-spaces;
  -webkit-font-variant-ligatures: none;
  font-variant-ligatures: none;
  font-feature-settings: "liga" 0; /* the above doesn't seem to work in Edge */
}

.ProseMirror [contenteditable="false"] {
  white-space: normal;
}

.ProseMirror [contenteditable="false"] [contenteditable="true"] {
  white-space: pre-wrap;
}

.ProseMirror pre {
  white-space: pre-wrap;
}

img.ProseMirror-separator {
  display: inline !important;
  border: none !important;
  margin: 0 !important;
  width: 0 !important;
  height: 0 !important;
}

.ProseMirror-gapcursor {
  display: none;
  pointer-events: none;
  position: absolute;
  margin: 0;
}

.ProseMirror-gapcursor:after {
  content: "";
  display: block;
  position: absolute;
  top: -2px;
  width: 20px;
  border-top: 1px solid black;
  animation: ProseMirror-cursor-blink 1.1s steps(2, start) infinite;
}

@keyframes ProseMirror-cursor-blink {
  to {
    visibility: hidden;
  }
}

.ProseMirror-hideselection *::selection {
  background: transparent;
}

.ProseMirror-hideselection *::-moz-selection {
  background: transparent;
}

.ProseMirror-hideselection * {
  caret-color: transparent;
}

.ProseMirror-focused .ProseMirror-gapcursor {
  display: block;
}

.tippy-box[data-animation=fade][data-state=hidden] {
  opacity: 0
}</style></head>

<body class="tab-width-8 gl-browser-chrome gl-platform-windows page-initialised" data-namespace-id="1167495" data-page="projects:tree:show" data-page-type-id="main/tp/1" data-project="b2e-cloud-2024" data-project-full-path="it4lik/b2e-cloud-2024" data-project-id="68004674" cz-shortcut-listen="true">

<script nonce="">
//<![CDATA[
gl = window.gl || {};
gl.client = {"isChrome":true,"isWindows":true};


//]]>
</script>


<header class="header-logged-out" data-testid="navbar">
<a class="gl-sr-only gl-accessibility" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#content-body">Skip to content</a>
<div class="container-fluid">
<nav aria-label="Explorer GitLab" class="header-logged-out-nav gl-flex gl-gap-3 gl-justify-between">
<div class="gl-flex gl-items-center gl-gap-1">
<span class="gl-sr-only">GitLab</span>
<a title="Page d&#39;accueil" id="logo" class="header-logged-out-logo has-tooltip" aria-label="Page d&#39;accueil" data-track-label="main_navigation" data-track-action="click_gitlab_logo_link" data-track-property="navigation_top" href="https://gitlab.com/"><svg aria-hidden="true" role="img" class="tanuki-logo" width="25" height="24" viewBox="0 0 25 24" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path class="tanuki-shape tanuki" d="m24.507 9.5-.034-.09L21.082.562a.896.896 0 0 0-1.694.091l-2.29 7.01H7.825L5.535.653a.898.898 0 0 0-1.694-.09L.451 9.411.416 9.5a6.297 6.297 0 0 0 2.09 7.278l.012.01.03.022 5.16 3.867 2.56 1.935 1.554 1.176a1.051 1.051 0 0 0 1.268 0l1.555-1.176 2.56-1.935 5.197-3.89.014-.01A6.297 6.297 0 0 0 24.507 9.5Z" fill="#E24329"></path>
  <path class="tanuki-shape right-cheek" d="m24.507 9.5-.034-.09a11.44 11.44 0 0 0-4.56 2.051l-7.447 5.632 4.742 3.584 5.197-3.89.014-.01A6.297 6.297 0 0 0 24.507 9.5Z" fill="#FC6D26"></path>
  <path class="tanuki-shape chin" d="m7.707 20.677 2.56 1.935 1.555 1.176a1.051 1.051 0 0 0 1.268 0l1.555-1.176 2.56-1.935-4.743-3.584-4.755 3.584Z" fill="#FCA326"></path>
  <path class="tanuki-shape left-cheek" d="M5.01 11.461a11.43 11.43 0 0 0-4.56-2.05L.416 9.5a6.297 6.297 0 0 0 2.09 7.278l.012.01.03.022 5.16 3.867 4.745-3.584-7.444-5.632Z" fill="#FC6D26"></path>
</svg>

</a></div>
<ul class="gl-list-none gl-p-0 gl-m-0 gl-flex gl-gap-3 gl-items-center gl-grow">
<li class="header-logged-out-nav-item header-logged-out-dropdown md:gl-hidden">
<button class="header-logged-out-toggle" data-toggle="dropdown" type="button">
<span class="gl-sr-only">
Menu
</span>
<svg class="s16" data-testid="hamburger-icon"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#hamburger"></use></svg>
</button>
<div class="dropdown-menu">
<ul>
<li>
<a href="https://about.gitlab.com/why-gitlab">Les raisons de choisir GitLab
</a></li>
<li>
<a href="https://about.gitlab.com/pricing">Tarification
</a></li>
<li>
<a href="https://about.gitlab.com/sales">Contacter le service commercial
</a></li>
<li>
<a href="https://gitlab.com/explore">Explorer</a>
</li>
</ul>
</div>
</li>
<li class="header-logged-out-nav-item gl-hidden md:gl-inline-block">
<a href="https://about.gitlab.com/why-gitlab">Les raisons de choisir GitLab
</a></li>
<li class="header-logged-out-nav-item gl-hidden md:gl-inline-block">
<a href="https://about.gitlab.com/pricing">Tarification
</a></li>
<li class="header-logged-out-nav-item gl-hidden gl-inline-block">
<a href="https://about.gitlab.com/sales">Contacter le service commercial
</a></li>
<li class="header-logged-out-nav-item gl-hidden md:gl-inline-block">
<a class="" href="https://gitlab.com/explore">Explorer</a>
</li>
</ul>
<ul class="gl-list-none gl-p-0 gl-m-0 gl-flex gl-gap-3 gl-items-center gl-justify-end">
<li class="header-logged-out-nav-item">
<a href="https://gitlab.com/users/sign_in?redirect_to_referer=yes">Connexion</a>
</li>
<li class="header-logged-out-nav-item">
<a class="gl-button btn btn-md btn-confirm !gl-inline-flex" href="https://gitlab.com/users/sign_up"><span class="gl-button-text">
Essai gratuit

</span>

</a></li>
</ul>
</nav>
</div>
</header>

<div class="layout-page page-with-super-sidebar">
<div><div class="super-sidebar-overlay"></div> <!----> <nav id="super-sidebar" aria-labelledby="super-sidebar-heading" data-testid="super-sidebar" class="super-sidebar"><h2 id="super-sidebar-heading" class="gl-sr-only">
      Navigation principale
    </h2> <div class="user-bar gl-flex gl-gap-1 gl-p-3"><div class="gl-flex gl-items-center gl-gap-1"><!----> <button aria-controls="super-sidebar" aria-expanded="true" aria-label="Barre latérale de navigation principale" type="button" class="btn btn-default btn-md gl-button btn-default-tertiary btn-icon js-super-sidebar-toggle-collapse" data-testid="super-sidebar-collapse-button"><!----> <svg data-testid="sidebar-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#sidebar"></use></svg>  <!----></button> <!----> <!----> <!----></div> <!----> <!----> <div class="gl-grow"><button id="super-sidebar-search" data-testid="super-sidebar-search-button" type="button" class="btn user-bar-button gl-border-none btn-default btn-md btn-block gl-button"><!----> <!---->  <span class="gl-button-text"><svg data-testid="search-icon" role="img" aria-hidden="true" class="gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#search"></use></svg>
      Rechercher ou aller à…
    </span></button> <!----></div></div> <div class="contextual-nav gl-flex gl-grow gl-flex-col gl-overflow-hidden"><div id="super-sidebar-context-header" class="super-sidebar-context-header gl-m-0 gl-px-4 gl-py-3 gl-font-bold gl-leading-reset">
        Projet
      </div> <div class="gl-scroll-scrim gl-overflow-auto gl-grow" data-testid="nav-container"><div class="top-scrim-wrapper"><div class="top-scrim"></div></div> <div></div> <div class="gl-relative gl-p-2"><!----> <!----> <!----> <ul aria-labelledby="super-sidebar-context-header" data-testid="non-static-items-section" class="gl-mb-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-project" data-testid="nav-item-link" aria-label="b2e-cloud-2024" data-track-action="click_menu_item" data-track-label="project_overview" data-track-property="nav_panel_project" data-qa-submenu-item="project-overview"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px; transform: translateX(-1px);"></div> <div class="gl-flex gl-w-6 gl-shrink-0 gl-self-start"><div class="gl-avatar gl-avatar-identicon gl-avatar-s24 gl-avatar-identicon-bg4">
  B
</div></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      b2e-cloud-2024
      <!----></div>  <!----></a> <!----></li><li><!----> <button id="menu-section-button-gestion" data-testid="menu-section-button" data-qa-section-name="Gestion" aria-controls="gestion" aria-expanded="false" data-qa-menu-item="Gestion" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="users-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#users"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Gestion
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="gestion" data-testid="menu-section" data-qa-section-name="Gestion" style="display: none;"><ul aria-label="Gestion" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/activity" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-project-activity" data-testid="nav-item-link" aria-label="Activité" data-track-action="click_menu_item" data-track-label="activity" data-track-property="nav_panel_project" data-qa-submenu-item="Activité"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Activité
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/project_members" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Membres" data-track-action="click_menu_item" data-track-label="members" data-track-property="nav_panel_project" data-qa-submenu-item="Membres"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Membres
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/labels" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Labels" data-track-action="click_menu_item" data-track-label="labels" data-track-property="nav_panel_project" data-qa-submenu-item="Labels"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Labels
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-programmation" data-testid="menu-section-button" data-qa-section-name="Programmation" aria-controls="programmation" aria-expanded="false" data-qa-menu-item="Programmation" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="planning-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#planning"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Programmation
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="programmation" data-testid="menu-section" data-qa-section-name="Programmation" style="display: none;"><ul aria-label="Programmation" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/issues" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-issues has-sub-items" data-testid="nav-item-link" aria-label="Tickets" data-track-action="click_menu_item" data-track-label="project_issue_list" data-track-property="nav_panel_project" data-qa-submenu-item="Tickets"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Tickets
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/boards" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-issue-boards" data-testid="nav-item-link" aria-label="Tableaux des tickets" data-track-action="click_menu_item" data-track-label="boards" data-track-property="nav_panel_project" data-qa-submenu-item="Tableaux des tickets"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Tableaux des tickets
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/milestones" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Jalons" data-track-action="click_menu_item" data-track-label="milestones" data-track-property="nav_panel_project" data-qa-submenu-item="Jalons"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Jalons
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/wikis/home" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-wiki" data-testid="nav-item-link" aria-label="Wiki" data-track-action="click_menu_item" data-track-label="project_wiki" data-track-property="nav_panel_project" data-qa-submenu-item="Wiki"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Wiki
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-code" data-testid="menu-section-button" data-qa-section-name="Code" aria-controls="code" aria-expanded="true" data-qa-menu-item="Code" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="code-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#code"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Code
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-on gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse show" id="code" data-testid="menu-section" data-qa-section-name="Code"><ul aria-label="Code" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/merge_requests" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-merge_requests" data-testid="nav-item-link" aria-label="Requêtes de fusion" data-track-action="click_menu_item" data-track-label="project_merge_request_list" data-track-property="nav_panel_project" data-qa-submenu-item="Requêtes de fusion"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Requêtes de fusion
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main" aria-current="page" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus super-sidebar-nav-item-current gl-px-3 gl-rounded-base shortcuts-tree" data-testid="nav-item-link" aria-label="Dépôt" data-track-action="click_menu_item" data-track-label="files" data-track-property="nav_panel_project" data-qa-submenu-item="Dépôt"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-10" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Dépôt
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/branches" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Branches" data-track-action="click_menu_item" data-track-label="branches" data-track-property="nav_panel_project" data-qa-submenu-item="Branches"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Branches
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/commits/main?ref_type=heads" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-commits" data-testid="nav-item-link" aria-label="Validations" data-track-action="click_menu_item" data-track-label="commits" data-track-property="nav_panel_project" data-qa-submenu-item="Validations"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Validations
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/tags" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Étiquettes" data-track-action="click_menu_item" data-track-label="tags" data-track-property="nav_panel_project" data-qa-submenu-item="Étiquettes"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Étiquettes
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/network/main?ref_type=heads" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-network" data-testid="nav-item-link" aria-label="Graphe du dépôt" data-track-action="click_menu_item" data-track-label="graphs" data-track-property="nav_panel_project" data-qa-submenu-item="Graphe du dépôt"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Graphe du dépôt
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/compare?from=main&amp;to=main" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Comparer les révisions" data-track-action="click_menu_item" data-track-label="compare" data-track-property="nav_panel_project" data-qa-submenu-item="Comparer les révisions"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Comparer les révisions
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/snippets" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-snippets" data-testid="nav-item-link" aria-label="Extraits de code" data-track-action="click_menu_item" data-track-label="project_snippets" data-track-property="nav_panel_project" data-qa-submenu-item="Extraits de code"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Extraits de code
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-compilation" data-testid="menu-section-button" data-qa-section-name="Compilation" aria-controls="compilation" aria-expanded="false" data-qa-menu-item="Compilation" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="rocket-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#rocket"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Compilation
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="compilation" data-testid="menu-section" data-qa-section-name="Compilation" style="display: none;"><ul aria-label="Compilation" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/pipelines" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-pipelines" data-testid="nav-item-link" aria-label="Pipelines" data-track-action="click_menu_item" data-track-label="pipelines" data-track-property="nav_panel_project" data-qa-submenu-item="Pipelines"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Pipelines
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/jobs" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-builds" data-testid="nav-item-link" aria-label="Jobs" data-track-action="click_menu_item" data-track-label="jobs" data-track-property="nav_panel_project" data-qa-submenu-item="Jobs"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Jobs
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/pipeline_schedules" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-builds" data-testid="nav-item-link" aria-label="Planifications de pipeline" data-track-action="click_menu_item" data-track-label="pipeline_schedules" data-track-property="nav_panel_project" data-qa-submenu-item="Planifications de pipeline"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Planifications de pipeline
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/artifacts" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-builds" data-testid="nav-item-link" aria-label="Artéfacts" data-track-action="click_menu_item" data-track-label="artifacts" data-track-property="nav_panel_project" data-qa-submenu-item="Artéfacts"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Artéfacts
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-deploiement" data-testid="menu-section-button" data-qa-section-name="Déploiement" aria-controls="deploiement" aria-expanded="false" data-qa-menu-item="Déploiement" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="deployments-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#deployments"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Déploiement
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="deploiement" data-testid="menu-section" data-qa-section-name="Déploiement" style="display: none;"><ul aria-label="Déploiement" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/releases" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-deployments-releases" data-testid="nav-item-link" aria-label="Releases" data-track-action="click_menu_item" data-track-label="releases" data-track-property="nav_panel_project" data-qa-submenu-item="Releases"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Releases
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/packages" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-container-registry" data-testid="nav-item-link" aria-label="Registre de paquets" data-track-action="click_menu_item" data-track-label="packages_registry" data-track-property="nav_panel_project" data-qa-submenu-item="Registre de paquets"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Registre de paquets
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/container_registry" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Registre de conteneur" data-track-action="click_menu_item" data-track-label="container_registry" data-track-property="nav_panel_project" data-qa-submenu-item="Registre de conteneur"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Registre de conteneur
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/ml/models" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Registre de modèles" data-track-action="click_menu_item" data-track-label="model_registry" data-track-property="nav_panel_project" data-qa-submenu-item="Registre de modèles"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Registre de modèles
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-operation" data-testid="menu-section-button" data-qa-section-name="Opération" aria-controls="operation" aria-expanded="false" data-qa-menu-item="Opération" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="cloud-pod-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#cloud-pod"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Opération
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="operation" data-testid="menu-section" data-qa-section-name="Opération" style="display: none;"><ul aria-label="Opération" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/environments" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-environments" data-testid="nav-item-link" aria-label="Environnements" data-track-action="click_menu_item" data-track-label="environments" data-track-property="nav_panel_project" data-qa-submenu-item="Environnements"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Environnements
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/terraform_module_registry" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Modules Terraform" data-track-action="click_menu_item" data-track-label="infrastructure_registry" data-track-property="nav_panel_project" data-qa-submenu-item="Modules Terraform"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Modules Terraform
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-surveillance" data-testid="menu-section-button" data-qa-section-name="Surveillance" aria-controls="surveillance" aria-expanded="false" data-qa-menu-item="Surveillance" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="monitor-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#monitor"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Surveillance
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="surveillance" data-testid="menu-section" data-qa-section-name="Surveillance" style="display: none;"><ul aria-label="Surveillance" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/incidents" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Incidents" data-track-action="click_menu_item" data-track-label="incidents" data-track-property="nav_panel_project" data-qa-submenu-item="Incidents"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Incidents
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/issues/service_desk" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Service d&#39;assistance" data-track-action="click_menu_item" data-track-label="service_desk" data-track-property="nav_panel_project" data-qa-submenu-item="Service d&#39;assistance"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Service d'assistance
      <!----></div>  <!----></a> <!----></li></ul></div></li><li><!----> <button id="menu-section-button-analyse" data-testid="menu-section-button" data-qa-section-name="Analyse" aria-controls="analyse" aria-expanded="false" data-qa-menu-item="Analyse" class="super-sidebar-nav-item gl-relative gl-mb-2 gl-flex gl-min-h-7 gl-w-full gl-appearance-none gl-items-center gl-gap-3 gl-rounded-base gl-border-0 gl-bg-transparent gl-px-3 gl-py-2 gl-text-left !gl-text-default !gl-no-underline focus:gl-focus"><span aria-hidden="true" class="gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-bg-transparent" style="width: 3px; border-radius: 3px; margin-right: 1px;"></span> <span class="gl-flex gl-w-6 gl-shrink-0"><svg data-testid="chart-icon" role="img" aria-hidden="true" class="super-sidebar-nav-item-icon gl-m-auto gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#chart"></use></svg></span> <span class="gl-truncate-end gl-grow gl-text-default">
      Analyse
    </span> <span class="gl-text-right gl-text-subtle"><svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="gl-animated-icon gl-animated-icon-off gl-animated-icon-current"><path d="M6.75 4.75L10 8L6.75 11.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="gl-animated-chevron-right-down-arrow"></path></svg></span></button> <!----> <div class="gl-m-0 gl-list-none gl-p-0 gl-duration-medium gl-ease-ease collapse" id="analyse" data-testid="menu-section" data-qa-section-name="Analyse" style="display: none;"><ul aria-label="Analyse" class="gl-m-0 gl-list-none gl-p-0"><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/value_stream_analytics" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-project-cycle-analytics" data-testid="nav-item-link" aria-label="Données d&#39;analyse des chaînes de valeur" data-track-action="click_menu_item" data-track-label="cycle_analytics" data-track-property="nav_panel_project" data-qa-submenu-item="Données d&#39;analyse des chaînes de valeur"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Données d'analyse des chaînes de valeur
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/graphs/main?ref_type=heads" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Analyse des contributeurs" data-track-action="click_menu_item" data-track-label="contributors" data-track-property="nav_panel_project" data-qa-submenu-item="Analyse des contributeurs"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Analyse des contributeurs
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/pipelines/charts" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Données d&#39;analyse CI/CD" data-track-action="click_menu_item" data-track-label="ci_cd_analytics" data-track-property="nav_panel_project" data-qa-submenu-item="Données d&#39;analyse CI/CD"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Données d'analyse CI/CD
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/graphs/main/charts" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base shortcuts-repository-charts" data-testid="nav-item-link" aria-label="Données d&#39;analyse du dépôt" data-track-action="click_menu_item" data-track-label="repository_analytics" data-track-property="nav_panel_project" data-qa-submenu-item="Données d&#39;analyse du dépôt"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Données d'analyse du dépôt
      <!----></div>  <!----></a> <!----></li><li data-testid="nav-item" class="show-on-focus-or-hover--context hide-on-focus-or-hover--context transition-opacity-on-hover--context gl-relative"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/ml/experiments" class="super-sidebar-nav-item show-on-focus-or-hover--control hide-on-focus-or-hover--control gl-relative gl-mb-1 gl-flex gl-min-h-7 gl-items-center gl-gap-3 gl-py-2 !gl-text-default !gl-no-underline focus:gl-focus gl-px-3 gl-rounded-base" data-testid="nav-item-link" aria-label="Expériences du modèle" data-track-action="click_menu_item" data-track-label="model_experiments" data-track-property="nav_panel_project" data-qa-submenu-item="Expériences du modèle"><div aria-hidden="true" data-testid="active-indicator" class="active-indicator gl-absolute gl-bottom-2 gl-left-2 gl-top-2 gl-transition-all gl-duration-slow gl-opacity-0" style="width: 3px; border-radius: 3px; margin-right: 1px;"></div> <div class="gl-flex gl-w-6 gl-shrink-0"><!----></div> <div data-testid="nav-item-link-label" class="gl-grow gl-text-default gl-break-anywhere">
      Expériences du modèle
      <!----></div>  <!----></a> <!----></li></ul></div></li></ul></div> <div id="sidebar-portal-mount"></div> <div></div> <div class="bottom-scrim-wrapper"><div class="bottom-scrim"></div></div></div> <!----> <div class="gl-p-2"><div class="gl-disclosure-dropdown gl-new-dropdown"><div id="dropdown-toggle-btn-1" data-testid="base-dropdown-toggle" class="gl-new-dropdown-custom-toggle"><button data-testid="sidebar-help-button" type="button" class="btn super-sidebar-help-center-toggle btn-with-notification btn-default btn-md gl-button btn-default-tertiary"><!----> <svg data-testid="question-o-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#question-o"></use></svg>  <span class="gl-button-text"><span data-testid="notification-dot" class="notification-dot-info"></span>
      Aide
    </span></button></div> <div id="base-dropdown-3" data-testid="base-dropdown-menu" class="gl-new-dropdown-panel !gl-w-31"><div class="gl-new-dropdown-arrow"></div> <div class="gl-new-dropdown-inner">  <ul id="disclosure-2" aria-labelledby="dropdown-toggle-btn-1" data-testid="disclosure-content" tabindex="-1" class="gl-new-dropdown-contents"> <!----> <li><!----> <ul class="gl-mb-0 gl-list-none gl-pl-0"><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="help" href="https://gitlab.com/help" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Aide
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="support" href="https://about.gitlab.com/get-help/" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Support
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="gitlab_documentation" href="https://gitlab.com/help/docs" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Documentation de GitLab
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="compare_gitlab_plans" href="https://about.gitlab.com/pricing" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Comparer les forfaits GitLab
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="community_forum" href="https://forum.gitlab.com/" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Forum de la communauté
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="contribute_to_gitlab" href="https://gitlab.com/help/_index.md#contribute-to-gitlab" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Contribuer à GitLab
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="submit_feedback" href="https://about.gitlab.com/submit-feedback" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Donner votre avis
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" data-track-property="nav_help_menu" data-track-action="click_link" data-track-label="privacy" href="https://about.gitlab.com/privacy" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper">
          Déclaration de confidentialité
        </span></a></li></ul></li> <li class="gl-border-t gl-border-t-dropdown-divider gl-pt-2 gl-mt-2"><!----> <ul class="gl-mb-0 gl-list-none gl-pl-0"><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><button tabindex="-1" data-track-action="click_button" data-track-label="keyboard_shortcuts_help" data-track-property="nav_help_menu" type="button" class="gl-new-dropdown-item-content js-shortcuts-modal-trigger"><span class="gl-new-dropdown-item-text-wrapper"><span class="-gl-my-1 gl-flex gl-items-center gl-justify-between">
        Raccourcis clavier
        <kbd aria-hidden="true" class="flat">?</kbd></span></span></button></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><button tabindex="-1" data-track-action="click_button" data-track-label="whats_new" data-track-property="nav_help_menu" type="button" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper"><span class="-gl-my-1 gl-flex gl-items-center gl-justify-between">
        Nouveautés
        <span class="gl-badge badge badge-pill badge-info" pill="" aria-hidden="true"><!----> <span class="gl-badge-content">4</span></span></span></span></button></li></ul></li></ul> </div></div></div> <!----> <div></div></div></div></nav> <a href="https://gitlab.com/explore/snippets" class="gl-hidden dashboard-shortcuts-snippets">
    Extraits de code
  </a><a href="https://gitlab.com/explore/groups" class="gl-hidden dashboard-shortcuts-groups">
    Groupes
  </a><a href="https://gitlab.com/explore/projects/starred" class="gl-hidden dashboard-shortcuts-projects">
    Projets
  </a> <!----> <!----></div>

<div class="content-wrapper">
<div class="broadcast-wrapper">




</div>
<div class="alert-wrapper alert-wrapper-top-space gl-flex gl-flex-col gl-gap-3 container-fluid container-limited">


























</div>
<div class="top-bar-fixed container-fluid" data-testid="top-bar">
<div class="top-bar-container gl-flex gl-items-center gl-gap-2">
<div class="gl-grow gl-basis-0 gl-flex gl-items-center gl-justify-start gl-gap-3">
<button aria-controls="super-sidebar" aria-expanded="false" aria-label="Barre latérale de navigation principale" type="button" class="btn btn-default btn-md gl-button btn-default-tertiary btn-icon gl-button btn btn-icon btn-md btn-default btn-default-tertiary js-super-sidebar-toggle-expand super-sidebar-toggle -gl-ml-3"><!----> <svg data-testid="sidebar-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#sidebar"></use></svg>  <!----></button>
<script type="application/ld+json">
{"@context":"https://schema.org","@type":"BreadcrumbList","itemListElement":[{"@type":"ListItem","position":1,"name":"it4","item":"https://gitlab.com/it4lik"},{"@type":"ListItem","position":2,"name":"b2e-cloud-2024","item":"https://gitlab.com/it4lik/b2e-cloud-2024"},{"@type":"ListItem","position":3,"name":"Dépôt","item":"https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main/tp/1"}]}


</script>
<div data-testid="breadcrumb-links" id="js-vue-page-breadcrumbs-wrapper">
<nav aria-label="Breadcrumb" class="gl-breadcrumbs" style=""><ol class="gl-breadcrumb-list breadcrumb"><!----> <li class="gl-breadcrumb-item gl-breadcrumb-item-sm"><a href="https://gitlab.com/it4lik" target="_self" class=""><!----><span class="gl-align-middle">it4</span></a></li><li class="gl-breadcrumb-item gl-breadcrumb-item-sm"><a href="https://gitlab.com/it4lik/b2e-cloud-2024" target="_self" class=""><!----><span class="gl-align-middle">b2e-cloud-2024</span></a></li><li class="gl-breadcrumb-item gl-breadcrumb-item-sm"><a aria-current="page" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main/tp/1" target="_self" class=""><!----><span class="gl-align-middle">Dépôt</span></a></li></ol></nav>
<div id="js-injected-page-breadcrumbs"></div>
</div>


</div>
<div class="gl-flex-none gl-flex gl-items-center gl-justify-center">
<!---->

</div>
<div class="gl-grow gl-basis-0 gl-flex gl-items-center gl-justify-end">
<div id="js-work-item-feedback"></div>


</div>
</div>
</div>

<div class="container-fluid container-limited project-highlight-puc">
<main class="content" id="content-body" itemscope="" itemtype="http://schema.org/SoftwareSourceCode">
<div class="flash-container flash-container-page sticky" data-testid="flash-container">
<!---->
</div>







<div class="tree-holder clearfix js-per-page gl-mt-5" data-blame-per-page="1000" id="tree-holder">
<section class=""><div class="tree-ref-container mb-2 mb-md-0 gl-flex gl-flex-wrap gl-gap-5"><div class="tree-ref-holder gl-max-w-26"><div class="ref-selector gl-w-full gl-new-dropdown !gl-block" data-testid="ref-dropdown-container"><button id="dropdown-toggle-btn-17" data-testid="base-dropdown-toggle" aria-haspopup="listbox" aria-expanded="false" aria-controls="base-dropdown-20" aria-labelledby="dropdown-toggle-btn-17" type="button" class="btn btn-default btn-md btn-block gl-button gl-font-monospace gl-mb-0 gl-new-dropdown-toggle"><!----> <!---->  <span class="gl-button-text gl-w-full"><span class="gl-new-dropdown-button-text">
        main
      </span> <svg data-testid="chevron-down-icon" role="img" aria-hidden="true" class="gl-button-icon gl-new-dropdown-chevron gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#chevron-down"></use></svg></span></button> <div id="base-dropdown-20" data-testid="base-dropdown-menu" class="gl-new-dropdown-panel !gl-w-31"><div class="gl-new-dropdown-arrow"></div> <div class="gl-new-dropdown-inner"> <div class="gl-flex gl-min-h-8 gl-items-center !gl-p-4 gl-border-b-1 gl-border-b-solid gl-border-b-dropdown-divider"><div id="listbox-header-19" data-testid="listbox-header-text" class="gl-grow gl-pr-2 gl-text-sm gl-font-bold gl-text-strong">
      Sélectionner une révision Git
    </div> <!----> <!----></div> <div class="gl-border-b-1 gl-border-b-solid gl-border-b-dropdown-divider"><div class="gl-listbox-search" data-testid="listbox-search-input"><svg data-testid="search-sm-icon" role="img" aria-hidden="true" class="gl-listbox-search-icon gl-icon s12 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#search-sm"></use></svg> <input type="search" aria-label="Rechercher par révision Git" placeholder="Rechercher par révision Git" class="gl-listbox-search-input"> <!----></div> <!----></div> <div id="listbox-18" aria-labelledby="listbox-header-19" role="listbox" tabindex="0" class="gl-new-dropdown-contents gl-new-dropdown-contents-with-scrim-overlay gl-new-dropdown-contents"><div aria-hidden="true" data-testid="top-scrim" class="top-scrim-wrapper"><div class="top-scrim top-scrim-dark"></div></div> <div aria-hidden="true"></div> <ul role="group" aria-labelledby="gl-listbox-group-53" class="gl-mb-0 gl-pl-0"><li id="gl-listbox-group-53" role="presentation" class="gl-pb-2 gl-pl-4 gl-pt-3 gl-text-sm gl-font-bold gl-text-strong">
      Branches <span class="gl-badge badge badge-pill badge-muted"><!----> <span class="gl-badge-content">1</span></span></li>  <li role="option" tabindex="-1" class="gl-new-dropdown-item" data-testid="listbox-item-refs/heads/main"><span class="gl-new-dropdown-item-content"><svg data-testid="dropdown-item-checkbox" role="img" aria-hidden="true" class="gl-icon s16 gl-fill-current gl-new-dropdown-item-check-icon gl-invisible gl-mt-3 gl-self-start"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#mobile-issue-close"></use></svg> <span class="gl-new-dropdown-item-text-wrapper">
      main
      <span class="gl-badge badge badge-pill badge-info"><!----> <span class="gl-badge-content">par défaut</span></span> <span class="gl-badge badge badge-pill badge-neutral" title="" size="sm"><!----> <span class="gl-badge-content">
  protégée
</span></span></span></span></li></ul> <!----> <!----> <div aria-hidden="true"></div> <div aria-hidden="true" data-testid="bottom-scrim" class="bottom-scrim-wrapper"><div class="bottom-scrim !gl-rounded-none"></div></div></div> <span data-testid="listbox-number-of-results" aria-live="assertive" class="gl-sr-only">
      1&nbsp;résultat
    </span>  </div></div></div> <!----></div> <nav aria-label="Fil d&#39;Ariane des fichiers" data-current-path="tp/1" class="js-repo-breadcrumbs gl-flex js-repo-breadcrumbs"><ol class="breadcrumb repo-breadcrumb"><li class="breadcrumb-item"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main" class="gl-link"><span>b2e-cloud-2024</span></a></li><li class="breadcrumb-item"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main/tp" class="gl-link"><span>tp</span></a></li><li class="breadcrumb-item"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/tree/main/tp/1" class="gl-link"><span>1</span></a></li><li class="breadcrumb-item"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md" aria-current="page" class="router-link-exact-active router-link-active gl-link"><strong>part4.md</strong></a></li> <!----></ol> <!----> <!----></nav></div> <div class="gl-flex gl-flex-col gl-items-stretch gl-justify-end sm:gl-flex-row sm:gl-items-center sm:gl-gap-5 gl-my-5"><h1 data-testid="repository-heading" class="gl-mt-0 gl-flex-1 gl-break-words gl-text-size-h1 sm:gl-my-0"><span aria-hidden="true" class="gl-mr-3 gl-inline-flex"><svg class="s16"><use href="/assets/file_icons/file_icons-59d148c7ea628b0ec3975493002fa45de1d4d8c15b2bf59775965ab9d67d62ab.svg#markdown"></use></svg></span>part4.md
    </h1> <!----> <div class="gl-flex gl-flex-wrap gl-items-center gl-gap-3"><!----> <button aria-keyshortcuts="t" data-testid="find" type="button" class="btn btn-default btn-md gl-button sm:gl-w-auto gl-w-full sm:gl-mt-0 gl-mt-3"><!----> <!---->  <span class="gl-button-text">
    Rechercher un fichier
  </span></button> <a data-testid="blame" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blame/main/tp/1/part4.md" class="btn js-blob-blame-link btn-default btn-md gl-button sm:gl-w-auto gl-w-full sm:gl-mt-0 gl-mt-3"><!----> <!---->  <span class="gl-button-text">
    Blame
  </span></a> <a aria-keyshortcuts="y" data-testid="permalink" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/ba51d2c58bdaa1a3f8c06c65d7e8173c3036461e/tp/1/part4.md" class="btn js-data-file-blob-permalink-url btn-default btn-md gl-button sm:gl-w-auto gl-w-full sm:gl-mt-0 gl-mt-3"><!----> <!---->  <span class="gl-button-text">
    Lien permanent
  </span></a> <!----></div></div></section>
<div class="info-well project-last-commit gl-flex-col gl-mt-5">
<div><div class="well-segment commit gl-flex gl-w-full !gl-px-5 !gl-py-4 gl-hidden sm:gl-flex"><a href="https://gitlab.com/it4lik" class="gl-avatar-link user-avatar-link js-user-link gl-my-2 gl-mr-3 gl-link gl-link-meta" data-username=""><span class=""><img src="./TP1_files/avatar.png" alt="Avatar de it4" class="gl-bg-cover gl-avatar gl-avatar-circle gl-avatar-s32" data-src="/uploads/-/system/user/avatar/969711/avatar.png?width=64" data-testid="user-avatar-image"> <!----></span> <!----> </a> <div class="commit-detail flex-list gl-flex gl-min-w-0 gl-grow"><div data-testid="commit-content" class="commit-content gl-inline-flex gl-w-full gl-flex-wrap gl-items-baseline"><div class="gl-inline-flex gl-basis-full gl-items-center gl-gap-x-3"><a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/commit/c7ae2fe239ec788cc71829c9fa031b8883ad17bd" class="commit-row-message item-title gl-line-clamp-1 gl-whitespace-normal !gl-break-all gl-link">meow</a> <!----></div> <div data-testid="committer" class="committer gl-basis-full gl-truncate gl-text-sm"><a href="https://gitlab.com/it4lik" class="commit-author-link js-user-link gl-link">
          it4</a>
        rédigé
        <time title="17 mars 2025 à 12:42:17 UTC+1" datetime="2025-03-17T12:42:17+01:00" class="">Il y a 13 heures</time></div> <!----></div> <div class="gl-grow"></div> <div class="commit-actions gl-my-2 gl-flex gl-items-start gl-gap-3"><!----> <!----> <div role="group" class="js-commit-sha-group gl-ml-4 gl-flex gl-items-center gl-button-group btn-group"><span variant="default" size="md" data-testid="last-commit-id-label" class="gl-font-monospace dark:!gl-bg-strong gl-button btn btn-label btn-md"><!----> <!---->  <span class="gl-button-text">c7ae2fe2</span></span> <button id="clipboard-button-60" title="Copier le SHA de la validation" data-clipboard-text="c7ae2fe239ec788cc71829c9fa031b8883ad17bd" data-clipboard-handle-tooltip="false" aria-label="Copier le SHA de la validation" aria-live="polite" type="button" class="btn input-group-text dark:!gl-border-l-section btn-default btn-md gl-button btn-default-secondary btn-icon"><!----> <svg data-testid="copy-to-clipboard-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#copy-to-clipboard"></use></svg>  <!----></button></div> <a data-testid="last-commit-history" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/commits/main/tp/1/part4.md" class="btn !gl-ml-0 btn-default btn-md gl-button btn-default-secondary"><!----> <!---->  <span class="gl-button-text">
        Historique
      </span></a></div></div> <!----></div> <div class="well-segment !gl-px-4 !gl-py-3 gl-block !gl-border-t-0 sm:gl-hidden"><div class="gl-flex gl-flex-wrap gl-items-center gl-justify-between"><div class="gl-flex gl-items-center gl-gap-3 gl-text-sm"><a href="https://gitlab.com/it4lik" class="gl-avatar-link user-avatar-link js-user-link gl-link gl-link-meta" data-username=""><span class=""><img src="./TP1_files/avatar.png" alt="Avatar de it4" class="gl-bg-cover gl-avatar gl-avatar-circle gl-avatar-s32" data-src="/uploads/-/system/user/avatar/969711/avatar.png?width=64" data-testid="user-avatar-image"> <!----></span> <!----> </a> <a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/commit/c7ae2fe239ec788cc71829c9fa031b8883ad17bd" class="commit-row-message item-title gl-line-clamp-1 gl-whitespace-normal !gl-break-all gl-link"><svg data-testid="commit-icon" role="img" aria-hidden="true" class="gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#commit"></use></svg>
        c7ae2fe2
      </a> <time title="17 mars 2025 à 12:42:17 UTC+1" datetime="2025-03-17T12:42:17+01:00" class="gl-text-subtle">Il y a 13 heures</time></div> <div class="gl-flex gl-items-center gl-gap-3"><button title="Afficher ou masquer la description du commit" aria-label="Afficher ou masquer la description du commit" data-testid="text-expander" type="button" class="btn text-expander btn-default btn-md gl-button btn-icon button-ellipsis-horizontal"><!----> <svg data-testid="ellipsis_h-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#ellipsis_h"></use></svg>  <!----></button> <a data-testid="collapsible-commit-history" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/commits/main/tp/1/part4.md" class="btn btn-default btn-sm gl-button"><!----> <!---->  <span class="gl-button-text">
        Historique
      </span></a></div></div> <!----></div></div>
</div>
<div class="gl-relative"><!----> <div id="fileHolder" class="file-holder"><div class="js-file-title file-title-flex-parent"><div class="gl-mb-3 gl-flex gl-gap-3 md:gl-mb-0"><div class="gl-disclosure-dropdown !gl-pr-0 gl-pr-2 gl-new-dropdown"><button id="dropdown-toggle-btn-61" data-testid="base-dropdown-toggle" aria-expanded="false" aria-controls="base-dropdown-68" aria-labelledby="dropdown-toggle-btn-61" type="button" class="btn btn-default btn-md gl-button gl-new-dropdown-toggle gl-new-dropdown-icon-only btn-icon"><!----> <svg data-testid="list-bulleted-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#list-bulleted"></use></svg>  <span class="gl-button-text"><span class="gl-new-dropdown-button-text">
        
      </span> <svg data-testid="chevron-down-icon" role="img" aria-hidden="true" class="gl-button-icon gl-new-dropdown-chevron gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#chevron-down"></use></svg></span></button> <div id="base-dropdown-68" data-testid="base-dropdown-menu" class="gl-new-dropdown-panel !gl-w-31"><div class="gl-new-dropdown-arrow"></div> <div class="gl-new-dropdown-inner">  <ul id="disclosure-62" aria-labelledby="dropdown-toggle-btn-61" data-testid="disclosure-content" tabindex="-1" class="gl-new-dropdown-contents"><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#user-content-part-iv--docker-security" target="_self" class="gl-new-dropdown-item-content" style="padding-left: 16px;"><span class="gl-new-dropdown-item-text-wrapper">
          Part IV : Docker security
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#user-content-sommaire" target="_self" class="gl-new-dropdown-item-content" style="padding-left: 24px;"><span class="gl-new-dropdown-item-text-wrapper">
          Sommaire
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#user-content-1-le-groupe-docker" target="_self" class="gl-new-dropdown-item-content" style="padding-left: 24px;"><span class="gl-new-dropdown-item-text-wrapper">
          1. Le groupe docker
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#user-content-2-scan-de-vuln" target="_self" class="gl-new-dropdown-item-content" style="padding-left: 24px;"><span class="gl-new-dropdown-item-text-wrapper">
          2. Scan de vuln
        </span></a></li><li tabindex="0" data-testid="disclosure-dropdown-item" class="gl-new-dropdown-item"><a tabindex="-1" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#user-content-3-petit-benchmark-secu" target="_self" class="gl-new-dropdown-item-content" style="padding-left: 24px;"><span class="gl-new-dropdown-item-text-wrapper">
          3. Petit benchmark secu
        </span></a></li></ul> </div></div></div> <div class="file-header-content gl-flex gl-items-center gl-leading-1"> <span aria-hidden="true"><svg class="s16 gl-mr-3"><use href="/assets/file_icons/file_icons-59d148c7ea628b0ec3975493002fa45de1d4d8c15b2bf59775965ab9d67d62ab.svg#markdown"></use></svg></span> <strong data-testid="file-title-content" class="file-title-name js-blob-header-filepath gl-mr-1 gl-break-all gl-font-bold gl-text-strong">part4.md</strong> <button id="clipboard-button-55" title="Copier le chemin du fichier" data-clipboard-text="{&quot;text&quot;:&quot;tp/1/part4.md&quot;,&quot;gfm&quot;:&quot;`tp/1/part4.md`&quot;}" data-clipboard-handle-tooltip="false" aria-label="Copier le chemin du fichier" aria-live="polite" type="button" class="btn btn-default btn-md gl-button btn-default-tertiary btn-icon gl-mr-2"><!----> <svg data-testid="copy-to-clipboard-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#copy-to-clipboard"></use></svg>  <!----></button> <small class="gl-mr-3 gl-text-subtle">2,85&nbsp;Kio</small> <!----></div></div> <div class="file-actions gl-flex gl-flex-wrap gl-gap-3"><div role="group" class="js-blob-viewer-switcher gl-button-group btn-group"><button aria-label="Afficher la source" title="Afficher la source" data-testid="simple-blob-viewer-button" data-viewer="simple" type="button" class="btn js-blob-viewer-switch-btn btn-default btn-md gl-button"><!----> <svg data-testid="code-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#code"></use></svg>  <span class="gl-button-text"></span></button> <button aria-label="Afficher le rendu du fichier" title="Afficher le rendu du fichier" data-testid="rich-blob-viewer-button" data-viewer="rich" type="button" class="btn js-blob-viewer-switch-btn btn-default btn-md gl-button selected"><!----> <svg data-testid="document-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#document"></use></svg>  <span class="gl-button-text"></span></button> <!----></div> <!----> <div class="sm:!gl-ml-0 sm:gl-ml-3" projectpath="it4lik/b2e-cloud-2024" projectid="68004674" gitref=""><div class="gl-disclosure-dropdown gl-new-dropdown !gl-block" data-testid="action-dropdown"><button id="dropdown-toggle-btn-56" data-testid="base-dropdown-toggle" aria-expanded="false" aria-controls="base-dropdown-58" aria-labelledby="dropdown-toggle-btn-56" type="button" class="btn btn-confirm btn-md btn-block gl-button gl-new-dropdown-toggle"><!----> <!---->  <span class="gl-button-text gl-w-full"><span class="gl-new-dropdown-button-text">
        Modifier
      </span> <svg data-testid="chevron-down-icon" role="img" aria-hidden="true" class="gl-button-icon gl-new-dropdown-chevron gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#chevron-down"></use></svg></span></button> <div id="base-dropdown-58" data-testid="base-dropdown-menu" class="gl-new-dropdown-panel"><div class="gl-new-dropdown-arrow"></div> <div class="gl-new-dropdown-inner">  <ul id="disclosure-57" aria-labelledby="dropdown-toggle-btn-56" data-testid="disclosure-content" tabindex="-1" class="gl-new-dropdown-contents"> <li class="edit-dropdown-group-width"><!----> <ul class="gl-mb-0 gl-list-none gl-pl-0"><li tabindex="0" data-testid="webide-menu-item" class="gl-new-dropdown-item"><button tabindex="-1" type="button" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper"><div class="gl-flex gl-flex-col"><span class="gl-mb-2 gl-flex gl-items-center gl-justify-between"><span data-testid="action-primary-text" class="gl-font-bold">Ouvrir dans Web EDI</span> <kbd class="flat">.</kbd></span> <span data-testid="action-secondary-text" class="gl-text-sm gl-text-subtle">
              Modifiez rapidement et facilement plusieurs fichiers de votre projet.
            </span></div></span></button></li><li tabindex="0" data-testid="edit-menu-item" class="gl-new-dropdown-item"><a tabindex="-1" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/edit/main/tp/1/part4.md" target="_self" class="gl-new-dropdown-item-content"><span class="gl-new-dropdown-item-text-wrapper"><div class="gl-flex gl-flex-col"><span class="gl-mb-2 gl-flex gl-items-center gl-justify-between"><span data-testid="action-primary-text" class="gl-font-bold">Modifier le fichier unique</span> <!----></span> <span data-testid="action-secondary-text" class="gl-text-sm gl-text-subtle">
              Modifiez ce fichier uniquement.
            </span></div></span></a></li></ul></li> </ul> </div></div></div> <!----></div>  <div role="group" class="gl-button-group btn-group" data-testid="default-actions-container"><button aria-label="Copier le contenu du fichier" title="Copier le contenu du fichier" data-testid="copy-contents-button" type="button" disabled="disabled" class="btn js-copy-blob-source-btn btn-default btn-md disabled gl-button btn-icon"><!----> <svg data-testid="copy-to-clipboard-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#copy-to-clipboard"></use></svg>  <!----></button> <a aria-label="Ouvrir la version brute" title="Ouvrir la version brute" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/raw/main/tp/1/part4.md" rel="noopener noreferrer" target="_blank" class="btn btn-default btn-md gl-button btn-icon"><!----> <svg data-testid="doc-code-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#doc-code"></use></svg>  <!----></a> <a aria-label="Télécharger" title="Télécharger" data-testid="download-button" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/raw/main/tp/1/part4.md?inline=false" rel="noopener noreferrer" target="_blank" class="btn btn-default btn-md gl-button btn-icon"><!----> <svg data-testid="download-icon" role="img" aria-hidden="true" class="gl-button-icon gl-icon s16 gl-fill-current"><use href="/assets/icons-aa2c8ddf99d22b77153ca2bb092a23889c12c597fc8b8de94b0f730eb53513f6.svg#download"></use></svg>  <!----></a> <!----></div></div></div> <!----> <div data-type="rich" class="blob-viewer js-syntax-highlight" data-loaded="true"><div current-ref="main" project-path="it4lik/b2e-cloud-2024" blob-path="tp/1/part4.md" blame-path="/it4lik/b2e-cloud-2024/-/blame/main/tp/1/part4.md" line-numbers="58" data-testid="blob-viewer-file-content"><div><div class="blob-viewer" data-path="tp/1/part4.md" data-rich-type="markup">
<div class="file-content js-markup-content md">
<h1 data-sourcepos="1:1-1:27" dir="auto">
<a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#part-iv--docker-security" aria-hidden="true" class="anchor" id="user-content-part-iv--docker-security"></a>Part IV : Docker security</h1>
<p data-sourcepos="3:1-3:84" dir="auto">Dans cette partie, on va survoler quelques aspects de Docker en terme de sécurité.</p>
<h2 data-sourcepos="5:1-5:11" dir="auto">
<a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#sommaire" aria-hidden="true" class="anchor" id="user-content-sommaire"></a>Sommaire</h2>
<ul data-sourcepos="7:1-12:0" dir="auto">
<li data-sourcepos="7:1-12:0">
<a data-sourcepos="7:3-7:56" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#part-iv--docker-security">Part IV : Docker security</a>
<ul data-sourcepos="8:3-12:0">
<li data-sourcepos="8:3-8:25"><a data-sourcepos="8:5-8:25" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#sommaire">Sommaire</a></li>
<li data-sourcepos="9:3-9:46"><a data-sourcepos="9:5-9:46" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#1-le-groupe-docker">1. Le groupe docker</a></li>
<li data-sourcepos="10:3-10:38"><a data-sourcepos="10:5-10:38" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#2-scan-de-vuln">2. Scan de vuln</a></li>
<li data-sourcepos="11:3-12:0"><a data-sourcepos="11:5-11:54" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#3-petit-benchmark-secu">3. Petit benchmark secu</a></li>
</ul>
</li>
</ul>
<h2 data-sourcepos="13:1-13:22" dir="auto">
<a href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#1-le-groupe-docker" aria-hidden="true" class="anchor" id="user-content-1-le-groupe-docker"></a>1. Le groupe docker</h2>
<p data-sourcepos="15:1-15:139" dir="auto">Si vous avez correctement ajouté votre utilisateur au groupe <code data-sourcepos="15:64-15:69">docker</code>, vous utilisez normalement Docker sans taper aucune commande <code data-sourcepos="15:134-15:137">sudo</code>.</p>
<blockquote data-sourcepos="17:1-17:165" dir="auto">
<p data-sourcepos="17:3-17:165">La raison technique à ça c'est que vous communiquez avec Docker en utilisant le socket <code data-sourcepos="17:93-17:112">/var/run/docker.sock</code>. Demandez-moi si vous voulez + de détails sur ça.</p>
</blockquote>
<p data-sourcepos="19:1-19:264" dir="auto">Cela découle sur le fait que vous avez les droits <code data-sourcepos="19:53-19:56">root</code> sur la machine. Sans utiliser aucune commande <code data-sourcepos="19:106-19:109">sudo</code>, sans devenir <code data-sourcepos="19:127-19:130">root</code>, sans même connaître son mot de passe ni rien, si vous êtes membres du groupe <code data-sourcepos="19:215-19:220">docker</code> vous pouvez devenir <code data-sourcepos="19:244-19:247">root</code> sur la machine.</p>
<p data-sourcepos="21:1-21:47" dir="auto"><gl-emoji title="sun with face" data-name="sun_with_face" data-unicode-version="8.0">🌞</gl-emoji> <strong data-sourcepos="21:6-21:47">Prouvez que vous pouvez devenir <code data-sourcepos="21:41-21:44">root</code></strong></p>
<ul data-sourcepos="23:1-29:0" dir="auto">
<li data-sourcepos="23:1-23:37">en étant membre du groupe <code data-sourcepos="23:31-23:36">docker</code>
</li>
<li data-sourcepos="24:1-24:65">sans taper aucune commande <code data-sourcepos="24:31-24:34">sudo</code> ou <code data-sourcepos="24:41-24:42">su</code> ou ce genre de choses</li>
<li data-sourcepos="25:1-25:53">normalement, une seule commande <code data-sourcepos="25:36-25:45">docker run</code> suffit</li>
<li data-sourcepos="26:1-29:0">pour prouver que vous êtes <code data-sourcepos="26:32-26:35">root</code>, plein de moyens possibles
<ul data-sourcepos="27:3-29:0">
<li data-sourcepos="27:3-27:96">par exemple un <code data-sourcepos="27:21-27:35">cat /etc/shadow</code> qui contient les hash des mots de passe de la machine hôte</li>
<li data-sourcepos="28:3-29:0">normalement, seul <code data-sourcepos="28:24-28:27">root</code> peut le faire</li>
</ul>
</li>
</ul>
<h2 dir="auto" data-sourcepos="30:1-30:18">
<a id="user-content-2-scan-de-vuln" class="anchor" aria-hidden="true" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#2-scan-de-vuln"></a>2. Scan de vuln</h2>
<p dir="auto" data-sourcepos="32:1-32:81">Il existe des outils dédiés au scan de vulnérabilités dans des images Docker.</p>
<p dir="auto" data-sourcepos="34:1-34:75">C'est le cas de <a rel="nofollow noreferrer noopener" href="https://github.com/aquasecurity/trivy" data-sourcepos="34:17-34:62" target="_blank">Trivy</a> par exemple.</p>
<p dir="auto" data-sourcepos="36:1-36:23"><gl-emoji data-unicode-version="8.0" data-name="sun_with_face" title="sun with face">🌞</gl-emoji> <strong data-sourcepos="36:6-36:23">Utilisez Trivy</strong></p>
<ul dir="auto" data-sourcepos="38:1-43:0">
<li data-sourcepos="38:1-43:0">effectuez un scan de vulnérabilités sur des images précédemment mises en oeuvre :
<ul data-sourcepos="39:3-43:0">
<li data-sourcepos="39:3-39:39">celle de WikiJS que vous avez build</li>
<li data-sourcepos="40:3-40:32">celle de sa base de données</li>
<li data-sourcepos="41:3-41:41">l'image de Apache que vous avez build</li>
<li data-sourcepos="42:3-43:0">l'image de NGINX officielle utilisée dans la première partie</li>
</ul>
</li>
</ul>
<h2 dir="auto" data-sourcepos="44:1-44:26">
<a id="user-content-3-petit-benchmark-secu" class="anchor" aria-hidden="true" href="https://gitlab.com/it4lik/b2e-cloud-2024/-/blob/main/tp/1/part4.md#3-petit-benchmark-secu"></a>3. Petit benchmark secu</h2>
<p dir="auto" data-sourcepos="46:1-46:186">Il existe plusieurs référentiels pour sécuriser une machine donnée qui utilise un OS donné. Un savoir particulièrement recherché pour renforcer la sécurité des serveurs surtout.</p>
<p dir="auto" data-sourcepos="48:1-48:302">Un des référentiels réputé et disponible en libre accès, ce sont <a rel="nofollow noreferrer noopener" href="https://www.cisecurity.org/cis-benchmarks" data-sourcepos="48:71-48:136" target="_blank">les benchmarks de CIS</a>. Ce sont ni plus ni moins que des guides complets pour sécuriser de façon assez forte une machine qui tourne par exemple sous Debian, Rocky Linux ou bien d'autres.</p>
<p dir="auto" data-sourcepos="50:1-50:186"><a rel="nofollow noreferrer noopener" href="https://github.com/docker/docker-bench-security" data-sourcepos="50:1-50:83" target="_blank">Docker développe un petit outil</a> qui permet de vérifier si votre utilisation de Docker est compatible avec les recommandations de CIS.</p>
<p dir="auto" data-sourcepos="52:1-52:51"><gl-emoji data-unicode-version="8.0" data-name="sun_with_face" title="sun with face">🌞</gl-emoji> <strong data-sourcepos="52:6-52:51">Utilisez l'outil Docker Bench for Security</strong></p>
<ul dir="auto" data-sourcepos="54:1-56:0">
<li data-sourcepos="54:1-54:91">rien à me mettre en rendu, je vous laisse exprimer votre curiosité quant aux résultats</li>
<li data-sourcepos="55:1-56:0">ce genre d'outils est cool d'un point de vue pédagogique : chaque check que fait le script c'est un truc à savoir finalement !</li>
</ul>
<p dir="auto" data-sourcepos="57:1-57:37"><a rel="noopener noreferrer" href="./TP1_files/secure.png" class="no-attachment-icon gfm" target="_blank"><img class="gfm js-lazy-loaded" decoding="async" alt="Docker is secure" src="./TP1_files/secure.png" data-sourcepos="57:1-57:37" loading="lazy" data-testid="js-lazy-loaded-content"></a></p>
</div>

</div>
</div></div></div> <!----></div> <!----></div>
</div>

<script nonce="">
//<![CDATA[
  window.gl = window.gl || {};
  window.gl.webIDEPath = '/-/ide/project/it4lik/b2e-cloud-2024/edit/main/-/tp/1'


//]]>
</script>
<div data-ambiguous="false" data-ref="main" id="js-ambiguous-ref-modal"></div>

</main>
</div>


</div>
</div>


<script nonce="">
//<![CDATA[
if ('loading' in HTMLImageElement.prototype) {
  document.querySelectorAll('img.lazy').forEach(img => {
    img.loading = 'lazy';
    let imgUrl = img.dataset.src;
    // Only adding width + height for avatars for now
    if (imgUrl.indexOf('/avatar/') > -1 && imgUrl.indexOf('?') === -1) {
      const targetWidth = img.getAttribute('width') || img.width;
      imgUrl += `?width=${targetWidth}`;
    }
    img.src = imgUrl;
    img.removeAttribute('data-src');
    img.classList.remove('lazy');
    img.classList.add('js-lazy-loaded');
    img.dataset.testid = 'js-lazy-loaded-content';
  });
}

//]]>
</script>
<script nonce="">
//<![CDATA[
gl = window.gl || {};
gl.experiments = {};


//]]>
</script>




<div></div><div></div></body></html>