<script>
    import {
        SITE_URL,
        SOCIAL_TITLE,
        SOCIAL_DESCRIPTION,
        SOCIAL_IMAGE,
        SOCIAL_IMAGE_ALT,
        INSTAGRAM_HANDLE,
        SITE_NAME,
        THEME_COLOR,
    } from "$lib/constants/seo.js";

    // Optional: Allow overriding defaults
    export let title = SOCIAL_TITLE;
    export let description = SOCIAL_DESCRIPTION;
    export let image = SOCIAL_IMAGE;
    export let imageAlt = SOCIAL_IMAGE_ALT;
    export let url = SITE_URL;
    export let instagramHandle = INSTAGRAM_HANDLE;
    export let twitterHandle = null;

    // Full URL for social image (important!)
    $: socialImageUrl = `${SITE_URL}${image}`;
</script>

<svelte:head>
    <!-- Primary Meta Tags -->
    <title>{title}</title>
    <meta name="title" content={title} />
    <meta name="description" content={description} />
    <meta
        name="keywords"
        content="movies, film reviews, cinema, movie analysis"
    />

    <!-- Open Graph / Facebook -->
    <meta property="og:type" content="website" />
    <meta property="og:url" content={url} />
    <meta property="og:title" content={title} />
    <meta property="og:description" content={description} />
    <meta property="og:image" content={socialImageUrl} />
    <meta property="og:image:alt" content={imageAlt} />
    <meta property="og:site_name" content={SITE_NAME} />

    <!-- Twitter -->
    <meta property="twitter:card" content="summary_large_image" />
    <meta property="twitter:url" content={url} />
    <meta property="twitter:title" content={title} />
    <meta property="twitter:description" content={description} />
    <meta property="twitter:image" content={socialImageUrl} />
    <meta property="twitter:image:alt" content={imageAlt} />
    {#if twitterHandle}
        <meta property="twitter:creator" content={twitterHandle} />
        <meta property="twitter:site" content={twitterHandle} />
    {/if}

    <!-- Additional Meta Tags -->
    <meta name="theme-color" content={THEME_COLOR} />
    <link rel="canonical" href={url} />
</svelte:head>
