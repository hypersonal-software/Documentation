---
title: Getting started
---

Learn how to use Hypersonal to personalize your shopify store for every customer with AI. {% .lead %}

<!-- {% quick-links %}

{% quick-link title="Shopify Installation" icon="installation" href="/" description="Detailed step-by-step guides to setting up Hypersonal in your Shopify store." /%}

{% quick-link title="Architecture guide" icon="presets" href="/" description="Learn how the internals work." /%}

{% quick-link title="Plugins" icon="plugins" href="/" description="Extend the library with third-party plugins or write your own." /%}

{% quick-link title="API Reference" icon="theming" href="/" description="Learn to use Hypersonal in your store regardless of the platform." /%}

{% /quick-links %} -->

Keep reading below for a quick introduction to getting started

1) Understanding what it Hypersonal is and how it works
1) Installing the app
1) Setting up traffic sources
1) Setting up theme blocks

---

## Important Concepts

![Hero Image](/images/hero-vector-image.svg)

Hypersonal provides the following theme blocks that can be used on your store's product pages. The content of these theme blocks adapt to the user viewing them using generative AI. The AI makes choices about what content to show based on the context the user is viewing the content in.

* Dynamic text blocks (headlines, paragraphs of full product descriptions)
* Option recommendations, such as color or size
* Product recommendations, such as replacement or commplementary
* Live Product Q&A and suggested questions

You can [view a demo of the theme blocks here](https://www.youtube.com/watch?v=nG0LqNYBEUA).

### How does Hypersonal work?
In order to make a decision about what content to show, Hypersonal looks at *context* clues about how the user got to the page. Right now Hypersonal uses direct context clues, meaning it doesn't look at third party cookies or other data to make decisions. The following context clues will work with Hypersonal

* Referring from a relevant page. For example referring to a Kettlebell store from a blog post titled "Best Kettlebell Exercises for Summer 2024".
* Direct hints you setup, passed through query parameters such as `?kw=` or `?q=`. You can add these to any links or campaigns you manage.
* UTM tracking parameters such as keywords passed from Google Ads. Note that this doesn't work for Google ads Performance Max shopping ads.

Hypersonal does not necessarily use all (or any) context clues. It depends on what it thinks is relevant to the product page. For example if referring from the CNN homepage to your Shoe Product page (congrats on that link, by the way), Hypersonal will like not use the referrer as a meaningful part of the context.

{% callout title="You should know!" %}
Using context from Google Ads requires some additional setup to ensure the appropriate contextual data is passed.
{% /callout %}

Personalized content is loaded in the background and does not block the user experience. A default text option is available for certain theme blocks, and is displayed if no existing dynamic content exists fitting for that context. Dynamic content is cached based on context for quick loading times (< 40ms). Content for a new context that is not similar enough to an existing context is generated in the background. This means the individual request that triggered it won't see it, but subsequent ones will. This is done to ensure that the user experience is smooth as perceived loading time is critical to a store's customer experience.

This means the first time any user hits your product page from a specific referring page, the default text will be shown (or the block will remain hidden if you have configured the block to not display the default text). Meanwhile we've registered that this context exists and will generate and store dynamic content for users coming from this referring page. Any user that comes from that same referring page in the future will then be shown dynamic content from the cache.

#### Metering
Because Hypersonal uses generative AI in the backend, generating dynamic text can be costly. In order to reflect the cost of the underlying computations, Hypersonal counts the number of generation events triggered for your store. The standard plan features 1,000 requests per month. If you go over this limit, subsequent calls to generate content will not be fulfilled.

You can view your current usage and plan's limit on the app's section of the admin dashboard.

![The status section of the admin dashboard shows generation request usage and limits](/images/screenshot_admin_status_limits.jpg)

## App Installation
Install the app through the Shopify app store (link to be updated). If you encounter any issues, don't hesitate to reach out to our support team at [support@hypersonal.com](mailto:support@hypersonal.com).

## Context Setup
### Referring Pages
Referring pages work automatically, as the referrer is always passed to Hypersonal. Not every referring page is used as a context to inform the generated content.

### UTM Parameters from Google Ads
Setting up google ads to pass parameters requires modifying your Tracking template. This can be done at multiple levels, most commonly the following 3.

1) The account level under Admin > Account Settings
1) The campaign level via the campaign settings panel > Additional Settins > Campaign URL Options
1) At the Ad level under Ad Url Options

All of these can be configured similarly, using the following tracking template `{lpurl}?keyword={keyword}`. You can include other parameters in the template if you want to, but at the minimum keyword is required for Hypersonal. You can find a list of all parameters and ways to setup tracking at this [Google Ads Help Article](https://support.google.com/google-ads/answer/6305348).

### Custom Query Parameters
You can also pass hints to Hypersonal via query parameters. Hypersonal looks for the following parameters: `q`, `kw`, `keyword`, `k`, `search`, `query`.

## Theme Block Setup

Theme blocks are managed via the built in Shopify theme editor. Themes offer a range of configuration options such as

* Default text behavior for when content is not available
* Simple A/B testing options
* Style and display options
* Behavioral options such as recommendation type or custom instructions

Installing theme blocks is as simple as dropping them into your template and configuring options.

## Testing Your Installation
If you want to test your theme block before anyone can access it, you can enable the require parameter option on the block.

![The theme editor view of the admin dashboard where you can require parameters](/images/screenshot_theme_require_param.jpg)

By checking this option you can ensure that normal users won't see any Hypersonal content. Only when you add the query parameter to the page will you see the block. You can do this yourself by modifying your product page url to add the appropriate query parameter. This depends on the block you want to see. For headlings for example this is `?dynamic-headline=true`. The informational text below the checkmark will tell you what the parameter is.

{% callout title="You should know!" %}
When using the require query parameter option, all A/B testing settings still apply. So you may not see the widget even if you have this checkbox enabled and the query parameter present.
{% /callout %}

To test your page you can hit your page with a request that looks like `{your product page}?dynamic-headline=true&kw={a relevant keyword}`. Replacing `{a relevant keyword}` with some keyword you want to test with. You may see the default text on the first request. After a few minutes try the request again and see if dynamic content is showing. If you require assistance confirming your setup is working, don't hesitate to reach out to our support team at [support@hypersonal.com](mailto:support@hypersonal.com)
---
## Getting help
If you run into any issues, have any questions, comments, or just want to chat feel free to drop a line to [support@hypersonal.com](mailto:support@hypersonal.com), we'd love to hear from you!
