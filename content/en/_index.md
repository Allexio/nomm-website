---
title: NOMM
description: Native Open Mod Manager
params:
  body_class: td-navbar-links-all-active
---

{{% blocks/cover
  title="NOMM: A simple & easy way to mod on linux!"
  height="full td-below-navbar"
  image_anchor="top"
%}}

<!--
  Want a cover without an image?
  Add the following argument to the blocks/cover shortcode:
    color="primary bg-gradient td-below-navbar"
-->

<!-- prettier-ignore -->
{{% _param description %}}
{.display-6}

<!-- prettier-ignore -->
<div class="td-cta-buttons my-5">
  <a {{% _param btn-lg primary %}} href="docs/">
    Learn more
  </a>
  <a {{% _param btn-lg secondary %}}
    href="{{% param github_repo %}}"
    target="_blank" rel="noopener noreferrer">
    Get the code
    {{% _param FA brands github "" %}}
  </a>
</div>

{{% blocks/link-down color="info" %}}

{{% /blocks/cover %}}

{{% blocks/lead color="white" %}}

NOMM provides a simple and modern solution for modding your games on Linux. It has support for over a dozen games, and adding support yourself is super easy (barely an inconvenience)!

No more faffing about trying to make vortex work on your distro, simply install the flatpak, follow the setup instructions and you're good to go!


{{% /blocks/lead %}}

{{% blocks/section color="primary" type="row" %}}

{{% blocks/feature title="New chair metrics!" icon="fa-lightbulb" %}}

The Goldydocs UI now shows chair size metrics by default.

Please follow this space for updates!

{{% /blocks/feature %}}

{{% blocks/feature
  title="Contributions welcome!" icon="fab fa-github"
  url="https://github.com/google/docsy-example"
%}}

We do a [Pull Request](https://github.com/google/docsy-example/pulls)
contributions workflow on **GitHub**. New users are always welcome!

{{% /blocks/feature %}}

{{% blocks/feature
  title="Follow us on X!" icon="fab fa-x-twitter"
  url="https://x.com/docsydocs"
%}}

For announcement of latest features etc.

{{% /blocks/feature %}}

{{% /blocks/section %}}

{{% blocks/section color="white" type="row text-center h1" %}}

This is the second section

{{% /blocks/section %}}

{{% blocks/section color="secondary" type="row text-center h1" %}}

This is the another section with center alignment

{{% /blocks/section %}}
