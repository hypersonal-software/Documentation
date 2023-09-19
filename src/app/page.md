---
title: Getting started
---

Learn how to use Hypersonal to personalize your ecommerce experience with AI. {% .lead %}

<!-- {% quick-links %}

{% quick-link title="Shopify Installation" icon="installation" href="/" description="Detailed step-by-step guides to setting up Hypersonal in your Shopify store." /%}

{% quick-link title="Architecture guide" icon="presets" href="/" description="Learn how the internals work." /%}

{% quick-link title="Plugins" icon="plugins" href="/" description="Extend the library with third-party plugins or write your own." /%}

{% quick-link title="API Reference" icon="theming" href="/" description="Learn to use Hypersonal in your store regardless of the platform." /%}

{% /quick-links %} -->

Keep reading below for a quick introduction to getting started on Shopify with some of the core features of Hypersonal.

---

## Important Concepts

We'll start by going over Context Providers, where Hypersonal gets data from as well as give you an understanding of how Hypersonal generates personalized content.
### Context Providers

Hypersonal refers to known data about a user as a context. This context is used to enable personalization features. Hypersonal uses large language models, and therefore relies heavily on natural language interpretations of these contexts.

You can think of a *context as any data reducable to a search intent*. This could be what was in the image of the ad they clicked, the audio transcript of a video ad, the search query related to a google ad click, the referring blog page that led them to your product page, etc.

<!-- ```shell
npm install @tailwindlabs/cache-advance
``` -->

As of the alpha version, Hypersonal supports the following context providers. In order to enable some of them you'll need to perform some additional setup.

* Google Ads ([Additional Setup Required](/docs/context-providers/google-ads))
* Meta Ads ([Additional Setup Required](/docs/context-providers/meta-ads))
* Referring Pages

<!-- {% callout type="warning" title="Oh no! Something bad happened!" %}
This is what a disclaimer message looks like. You might want to include inline `code` in it. Or maybe you’ll want to include a [link](/) in it. I don’t think we should get too carried away with other scenarios like lists or tables — that would be silly.
{% /callout %} -->

### Asynchronous Content Generation
All of Hypersonal's features rely on content stored in Hypersonal's backend. Information about the user context is passed to Hypersonal's API, regardless of the integration, and a piece of dynamic content is retrieved. Dynamic content is only retrieved for display from existing pools of data. Whenever a new context is encountered globally, a backend process is triggered to generate personalized content for that context.

Hypersonal doesn't block the page loading on new dynamic content generation. Dynamic content generation always happens asynchronously. This is because it is dependent on large language models which can take seconds to minutes to generate content. Far too long for a user to be shown a loading indicator.

When a context is hit, a request is sent to the server to get the context dynamically. If it fails to find anything, a background request to generate the content is triggered. Within a few minutes the dynamic content matching this specific context should be available. Subsequent visits from the same context are then served this dynamic content. This means the first time anyone clicks on an ad, uses a specific keyword, etc. it won't be available to them. But afterward it will be available to all users.

#### Example
Let's look at a concrete example involving two users, Gerald and Paul. One of your partner sites, topfishercool.com published a piece of content that has just gotten indexed in google. Gerald visits your product page that has dynamic product descriptions enabled. He got there after searching for "Best fishing rod for bass fishing" on google and clicking through a blog post about the best fishing rods for bass fishing on topfishercool.com. Gerald is the *first person ever* to click through that link and will experience the page without the dynamic content. He will be shown the default product description.

Suppose now Paul comes about 5 minutes later. By now Gerald's visit will have triggered a request in Hypersonal's backend to generate a product description for this context (topfishercool.com's best fishing rods for bass fishing blog post). Now Paul is shown a dynamic product description, tailored to how the product is well suited for bass fishing rather than the default product description.

{% callout title="You should know!" %}
Prepopulating dynamic content is a feature coming in the future. However there will always be a chance that a user will see the non-personalized experience. For example for long tail keywords, newly created campaigns that are extremely recent, or if the content generation queue is backed up.
{% /callout %}

## Quick Start

### App Installation
Install the app through the Shopify store. If you encounter any issues, don't hesitate to reach out to our support team.

### Feature Setup

Hypersonal is a set of personalization features that you can enable visually on your store. For Shopify users these can be added through theme blocks. You can access these theme blocks in the theme editor. The Theme Editor can be accessed from the Shopify Admin dashboard through Sales Channels > Online Store > Themes, and then clicking the customize button as pictured below.

![The online store Themes page with the Customize button highlighted](/images/screenshot_edit_theme.jpg)

{% callout title="You should know!" %}
While you can setup most things through the theme blocks themselves, there are also configuration options available on the app page itself. Things like the keyword block list or global instructions for example. These are available in the Hypersonal app page under the Apps navigation.
{% /callout %}

---

## Feature Introduction

We'll cover the core features of Hypersonal and how to use them.

### Dynamic Headlines

Dynamic headlines are personalized generated content inserted into headlines on a product page. You can find out more about the practical applications of Dynamic Headlines on our [blog](https://www.hypersonal.com/blog/why-and-how-dynamic-headlines-increase-purchase-intent).

The main idea behind dynamic headlines is that they increase purchase intent by tying the product page to the user's search intent.

![Dynamic headline for Dachshunds appearing on a product page for a dog bed](/images/screenshot_dynamic_headline.jpg)

The above example shows the product page for a dog bed with a dynamic headline. The context here is the user having searched for "Dog Bed for Dachshund" and clicking through a google ad. Dynamic headlines are easy to use. You simply add the dynamic headline to the Product Page Template.

![The dynamic headline block on a product page template](/images/dynamic_headline_in_editor.jpg)

You can learn more about [Dynamic Headlines here](/docs/features/dynamic-headlines).

### Clearing the cache

Vel aut velit sit dolor aut suscipit at veritatis voluptas. Laudantium tempore praesentium. Qui ut voluptatem.

Ea est autem fugiat velit esse a alias earum. Dolore non amet soluta eos libero est. Consequatur qui aliquam qui odit eligendi ut impedit illo dignissimos.

Ut dolore qui aut nam. Natus temporibus nisi voluptatum labore est ex error vel officia. Vero repellendus ut. Suscipit voluptate et placeat. Eius quo corporis ab et consequatur quisquam. Nihil officia facere dolorem occaecati alias deleniti deleniti in.

### Adding middleware

Officia nobis tempora maiores id iusto magni reprehenderit velit. Quae dolores inventore molestiae perspiciatis aut. Quis sequi officia quasi rem officiis officiis. Nesciunt ut cupiditate. Sunt aliquid explicabo enim ipsa eum recusandae. Vitae sunt eligendi et non beatae minima aut.

Harum perferendis aut qui quibusdam tempore laboriosam voluptatum qui sed. Amet error amet totam exercitationem aut corporis accusantium dolorum. Perspiciatis aut animi et. Sed unde error ut aut rerum.

Ut quo libero aperiam mollitia est repudiandae quaerat corrupti explicabo. Voluptas accusantium sed et doloribus voluptatem fugiat a mollitia. Numquam est magnam dolorem asperiores fugiat. Soluta et fuga amet alias temporibus quasi velit. Laudantium voluptatum perspiciatis doloribus quasi facere. Eveniet deleniti veniam et quia veritatis minus veniam perspiciatis.

---

## Getting help

Consequuntur et aut quisquam et qui consequatur eligendi. Necessitatibus dolorem sit. Excepturi cumque quibusdam soluta ullam rerum voluptatibus. Porro illo sequi consequatur nisi numquam nisi autem. Ut necessitatibus aut. Veniam ipsa voluptatem sed.

### Submit an issue

Inventore et aut minus ut voluptatem nihil commodi doloribus consequatur. Facilis perferendis nihil sit aut aspernatur iure ut dolores et. Aspernatur odit dignissimos. Aut qui est sint sint.

Facere aliquam qui. Dolorem officia ipsam adipisci qui molestiae. Error voluptatem reprehenderit ex.

Consequatur enim quia maiores aperiam et ipsum dicta. Quam ut sit facere sit quae. Eligendi veritatis aut ut veritatis iste ut adipisci illo.

### Join the community

Praesentium facilis iste aliquid quo quia a excepturi. Fuga reprehenderit illo sequi voluptatem voluptatem omnis. Id quia consequatur rerum consectetur eligendi et omnis. Voluptates iusto labore possimus provident praesentium id vel harum quisquam. Voluptatem provident corrupti.

Eum et ut. Qui facilis est ipsa. Non facere quia sequi commodi autem. Dicta autem sit sequi omnis impedit. Eligendi amet dolorum magnam repudiandae in a.

Molestiae iusto ut exercitationem dolorem unde iusto tempora atque nihil. Voluptatem velit facere laboriosam nobis ea. Consequatur rerum velit ipsum ipsam. Et qui saepe consequatur minima laborum tempore voluptatum et. Quia eveniet eaque sequi consequatur nihil eos.
