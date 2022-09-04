# Tsconfig paths only for ts files


## TLDR

- Nextjs

    Modify `next.config.js` like this:
    ```javascript
    const path = require("node:path");

    /** @type {import('next').NextConfig} */
    const nextConfig = {
        reactStrictMode: true,
        swcMinify: true,
        webpack: (
            config,
            { buildId, dev, isServer, defaultLoaders, nextRuntime, webpack }
        ) => {
            config.resolve.alias["@styles"] = path.resolve(__dirname, "styles");
            return config;
        },
    };

    module.exports = nextConfig;
    ```


## The Story

Path alias is great to avoid import by relative path from deep nested file.
Also, its nice and readable.
But tsconfig is only for typescript, not for styles.


## Environment
- Language:
    - typescript
- Framework:
    - webpack
    - nextjs@12


## Issue
- Degree: i-didnt-know-that
- Keywords:
    - tsconfig paths not for styles
    - alias for styles
    - alias for non-typescript path
- References:
    - https://github.com/angular/angular-cli/issues/9018
    - https://webpack.js.org/configuration/resolve/
    - https://nextjs.org/docs/api-reference/next.config.js/custom-webpack-config
