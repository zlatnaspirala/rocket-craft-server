
# Rocket Craft Server 
## for Rocket Craft (ue4 project) clients.
## General status : `underconstruct`

Basic account session staff based on node.js and MongoDB.

 Integration done:

 - Node.js http1.1/http2 server
 - Basic session account support (mongoDB)
 - Vue-Typescript administrator panel project
 - Test clients (rocket-craft repo)

### Run rocketcraftingserver in local (dev):
![](https://github.com/zlatnaspirala/rocket-craft-server/blob/main/non-project-files/tutorial-steps/local-run-rocket-crafting-server.gif)

### Run Admin panel
![](https://github.com/zlatnaspirala/rocket-craft-server/blob/main/non-project-files/tutorial-steps/local-run-rocket-crafting-admin-panel.gif)


### Project structure ###

 - First char in name `I` (for example IApp.ts) represent 
   current interface used for generating API documentation.
 - Dont upload this project in www, htdocs, public folder
   on you public domain mashine. Like any node.js app.
 - Folder `admin-panel` is somekind of sandbox.
   Dont import any file from root like congif.js.
   Even admin access it is still posible for public access.
 - Top secret list:
      - system email password
      - public database password

<pre>

├── database/
|   ├── data/                    (internal mongodb generated)
├── docs/                        (Output for documentation html)
├── node_modules/                (auto generated)
├── admin-panel/                 [Vue - admin app]
|   ├── dist/                    (auto generated)
|   ├── images/
|   |   └── icons/
|   |   |   └── svgs
|   |   |   └── pngs
|   ├── node_modules/            (auto generated)
|   ├── public/                  [Vue - Public]
|   ├── src/                     [Vue - src]
|   |   └── components/            
|   |       └── administrator/
|   |           └── accounts.vue
|   |   └── local-storage/
|   |   └── my-common/
|   |       └── common-func.ts
|   |       └── literal.ts
|   |   └── styles/
|   |   └── App.vue
|   |   └── IApp.ts
|   |   └── main.ts
|   |   └── error-instance.ts
|   |   └── shims-tsx.d.ts
|   |   └── shims-vue.d.ts
|   |   └── store.ts
|   ├── .eslintignore
|   ├── .gitignore
|   ├── babel.config.js
|   ├── index.html
|   ├── manifest.web          [PWA - staff]
|   ├── package.json
|   ├── package-lock.json
|   ├── typedoc.json          [Documentation generator config]
|   ├── tsconfig.ts
|   ├── vue.config.js         [PWA - staff]
├── self-cert/                [server side local cert]
├── mu;tiplayer/              (raw implementation - support servers)
├── .gitignore        
├── config.js                 [server side config]
├── LICENCE
├── README.md
├── package.json                
├── package-lock.json
├── server.js                   [Main Server]

</pre>

#### Active RocketCraftServer integrated Features List:

<pre>
 - MongoDB integrated      [DONE]
 - Switch theme (style)    [DONE]
   (whole palette ofo colors)
 - Test account route
    - register              [DONE]
    - register confirmaton  [DONE]
    - login                 [DONE]
    - user                  [DONE]
    - test ue4 clients part [DONE]
 - Basic http/https server  [DONE]
</pre>

#### Active RocketCraftClient engine 4.22 integrated Features List:

Client application (all platforms releases/builds) use communication
with rocketCraftServer only on `API` level with http/https protocol.

Only implications between client vs server is account session status
(in database field online). Logged or not.
<pre>
 - Account routes
    - register form        [DONE]
    - reg/confirmaton form [DONE]
    - login form           [DONE]
    - profile              [DONE]
</pre>

<pre>
+-------------------------------------------------------------------------------------------------------+
|                                                                                                       |
|  +-----------------------------------------------------+                                              |
|  SOURCE : https://github.com/zlatnaspirala/rocket-craft                                               |
|  +-----------------------------------------------------+                                              |
|                                                                                                       |
|                                                                                                       |
|      DESKTOPS                            MOBILE     GameConsoles          WEB                         |
| +-------------------------------+   +------------------------------+  +----------------------------+  |
| |                               |   |                              |  |                            |  |
| |   WINDOWS                     |   |  ANDROID       X-Box         |  | Unreal export direct from  |  |
| |                               |   |                              |  | 4.22 or use engine 4.24    |  |
| |   MACOS                       |   |  IOS                         |  | (build from source)        |  |
| |                               |   |                              |  |                            |  |
| |                               |   |                              |  | AdminPanel (THIS REPO)     |  |
| |                               |   |                              |  |                            |  |
| |   LINUX                       |   |  etc                         |  | Also can be used by any    |  |
| |                               |   |                              |  | web application            |  |
| +-------------------------------+   +------------------------------+  +----------------------------+  |
|                                    rocket Client builds                                               |
+----------+----------+---------------------------------------------------------------------------------+
           ^          |
           |          |        MATCHMAKING
           |          |
           |          |        SINGNALING SERVER
           |          |
           |          |        WEB SERVER
           |          |
+-------------------------------------------------------------------------------------------------------+
|          |          |                                                                                 |
|     +----+----------v--------+                                      +-----------------------------+   |
|     |                        |                                      |                             |   |
|     |      REST API          |                                      |  HTTP, HTTPS (1.1 or 2)     |   |
|     | [/rocket/register]     |                                      |                             |   |
|     | [/rocket/confirmation] |                                      +-----------------------------+   |
|     | [/rocket/register]     |                                                                        |
|     | [/rocket/login]        |                                                                        |
|     | [/rocket/profile]      |                                                                        |
|     +------------------------+                                                                        |
|                                                                                                       |
|  +------------------------------------------------------------+                                       |
|  SOURCE : https://github.com/zlatnaspirala/rocket-craft-server                                        |
|  +------------------------------------------------------------+                                       |
|                                                                                                       |
+-------------------------------------------------------------------------------------------------------+
|                                            NODEJS CORE                                                |
+-------------------------------------------------------------------------------------------------------+
|                                           MONGO DATABASE                                              |
+-------------------------------------------------------------------------------------------------------+

</pre>

### Features in WIP status:

  - Admin Panel (Vue-ClassComponent-Typescript)

  - Debugging proccess for server part with Visual-Code.
    (Launch.json tested on windows)`
    create folder `.vscode` in root of workspace and copy `launch.json`.

    Please use debugger and learn and feel node iterrator flow.

 - Rocket server
   - Get active servers list
   - Open game session
