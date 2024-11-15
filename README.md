# LG-TV-webOS-app-how-to-guide

> [!WARNING]  
> This is a WIP
> 
> This may have incorrect information, better solutions may exist
> 
> This is really geared towards my current situation which is WebOS 4 and Enact 1.13 but may be helpful to you

## TODO

- Enable developer mode
- Creating LG developer account
- Installing ares

## Creating LG developer account

Can be created on the [LG website](https://us.lgemembers.com/lgacc/service/v1/signin)

If email address has previously been used with LG, or complains about used in a different country (for me I'm Canadian and the LG dev site seems to be United States), use a different email account.
If using an email account that supports '+' or '.' that will work as well ex `+dev@gmail.com`.

## Enact and WebOS versioning

Enact is a framework built on top of React and one of its uses is building out WebOS applications.

> [!NOTE]
> 
> It's important to ensure that the version of Enact you're using
matches the WebOS version of your TV

For LG, you can find the Platform version under -> Settings menu: Settings > General > TV Information > webOS TV version

[This page](https://webostv.developer.lge.com/develop/guides/enyo-enact-guide) explains what version of Enact is suitable for your TV.

[This page explains the Chromium web engine that the WebOS version is](https://webostv.developer.lge.com/develop/specifications/web-api-and-web-engine).

Example:

"webOS TV 4.x" requires Enact 1.13. Create a sample app and update all the supported `@enact/*` dependencies
with 1.13 and `npm install`

### Why use Enact

At this point I'm still trying to figure that out. What I do know is enact:

- Handles packaging for you
- Keeps the WebOS metadata separate and source code in `src/` is just React code. Nice separation
- Comes with linting
- Comes with `enact test` out of the box (TODO what is this)

## Getting app to deploy to TV

`enact pack` which compiles the code inside a `dist/` directory for development
`enact pack-p` compiles the code inside a `dist/` directory for production

`ares-package dist` creates the IPK that will be installed on the TV

`ares-install --device <TARGET_DEVICE> <IPK FILE>`

## Other documentation

[Sample apps by WebOS](https://webostv.developer.lge.com/develop/samples)
