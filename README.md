# Angular Boilerplate

Angular starter for enterprise-grade front-end projects, built under a clean architecture that helps to scale and maintain a fast workflow.

## โ๏ธ Features

- Strict mode.
- Lazy loading.
- Smart and pure components pattern.
- Components types (e.g. component, page).
- Self-contained components and encapsulated modules.
- Auth scheme
- Settings scheme
- User scheme
- PWA
- i18n
- Dynamic titles and content meta tags.
- TailwindCSS + Autoprefixer + PurgeCSS setup.
- Dark mode and theme configuration.
- Scalable CSS architecture in favor of TailwindCSS layers.
- [Lighthouse](https://developers.google.com/web/tools/lighthouse) reports improved.
- Migration from TSLint to ESLint.
- ESLint migration.

## ๐ Pages

- General
  - home
  - not-found
- Auth
  - sign-in
  - sign-up
  - forgot-password
  - forgot-password-email-sent
  - password-reset
  - password-reset-succeeded
  - password-reset-failed
- Settings
  - account
  - appearance
  - billing
  - blocked-Users
  - notifications
  - security
  - security-log
- User
  - my-profile
  - overview
- Features
  - dashboard

## ๐งฑ Self-contained components

- breadcrumb
- footer
- header
- theme-panel

## ๐ก Services

- AuthService
- SeoService
- ThemeService

## ๐ Custom directives

- click-outside (detects when the user clicks outside an element).

## ๐งช Custom pipes

- bytes (transforms a numeric value into bytes, KB, MB, GB, etc.).

## ๐ ๏ธ Make some initial tweaks

- Change application title:

  Go to `src/index.html` and inside the `title` tag, replace "Angular Boilerplate" with your app name.

- Change paths of the pages:

  Go to `src/app/core/structs/path.enum.ts` to find all the registered routes in an enum file.

  For example, you could replace `sign-in` with `SignIn`, `login` or `iniciar_sesion`

- Change titles, descriptions, and robots of the pages:

  Every page has a `.route` file that contains an exported constant that holds the title, description and a robot's metatag that indicates if it can be indexed or followed by a web crawler.

- Change your TailwindCSS configuration:

  You can find the config file in the project root, then you can refer to https://tailwindcss.com/docs/configuration to learn how to make your own adjustments.

- Change light and dark mode colors:

  Go to `src/theme/01-base/variables.scss` and change them to your preference.

- Set a default theme (First time load)

  Go to `src\app\@core\services\theme\theme.service.ts` and change the following line of code:

  from operating system preference

  ```ts
  private currentTheme$ = new BehaviorSubject<ThemeList>(
    this.currentTheme || ThemeList.System
  );
  ```

  to light mode

  ```ts
  private currentTheme$ = new BehaviorSubject<ThemeList>(
    this.currentTheme || ThemeList.Light
  );
  ```

  or dark mode

  ```ts
  private currentTheme$ = new BehaviorSubject<ThemeList>(
    this.currentTheme || ThemeList.Dark
  );
  ```

## โฉ๏ธ Project structure

```console
โโโโapp
โ   โโโโ+auth
โ   โ   โโโโpages
โ   โ   โ   โโโโforgot-password
โ   โ   โ   โโโโforgot-password-email-sent
โ   โ   โ   โโโโpassword-reset
โ   โ   โ   โโโโpassword-reset-failed
โ   โ   โ   โโโโpassword-reset-succeeded
โ   โ   โ   โโโโsign-in
โ   โ   โ   โโโโsign-up
โ   โ   โโโโservices
โ   โโโโ+settings
โ   โ   โโโโpages
โ   โ       โโโโaccount
โ   โ       โโโโappearance
โ   โ       โโโโbilling
โ   โ       โโโโblocked-users
โ   โ       โโโโnotifications
โ   โ       โโโโsecurity
โ   โ       โโโโsecurity-log
โ   โโโโ+user
โ   โ   โโโโpages
โ   โ       โโโโmy-profile
โ   โ       โโโโoverview
โ   โโโโ@components
โ   โ   โโโโbreadcrumb
โ   โ   โโโโfooter
โ   โ   โโโโheader
โ   โ   โโโโtheme-panel
โ   โโโโ@containers
โ   โ   โโโโhome
โ   โ   โโโโnot-found
โ   โโโโ@core
โ   โ   โโโโdirectives
โ   โ   โ   โโโโclick-outside
โ   โ   โโโโguards
โ   โ   โโโโinterceptors
โ   โ   โโโโpipes
โ   โ   โ   โโโโbytes
โ   โ   โโโโservices
โ   โ   โ   โโโโseo
โ   โ   โ   โโโโtheme
โ   โ   โโโโstructs
โ   โ   โโโโutils
โ   โโโโfeatures
โ       โโโโdashboard
โโโโassets
โโโโenvironments
โโโโpublic
โ   โโโโicons
โโโโtheme
    โโโโ01-base
    โโโโ02-components
    โโโโ03-utilities
```

## ๐งโโ๏ธ Commands

| Command      | Description                                      | NPM                | Yarn            | Background command                                              |
| ------------ | ------------------------------------------------ | ------------------ | --------------- | --------------------------------------------------------------- |
| ng           | See available commands                           | npm run ng         | yarn ng         | ng                                                              |
| dev          | Run your app in development mode & open app      | npm run dev        | yarn dev        | ng serve -o                                                     |
| start        | Run your app in development mode                 | npm start          | yarn start      | ng serve                                                        |
| start:es     | Run your app in development mode in spanish      | npm run start:es   | yarn start:es   | ng serve -c=es --port 4201                                      |
| build        | Build your app                                   | npm run build      | yarn build      | ng build                                                        |
| build:prod   | Build your app ready for production              | npm run build:prod | yarn build:prod | ng build --prod --build-optimizer --aot --stats-json            |
| build:i18n   | Build your multilingual app ready for production | npm run build:i18n | yarn build:i18n | ng build --prod --build-optimizer --aot --stats-json --localize |
| test         | Run your unit tests                              | npm run test       | yarn test       | ng test                                                         |
| lint         | Use ESLint to lint your app                      | npm run lint       | yarn lint       | ng lint                                                         |
| e2e          | Run your e2e integration tests                   | npm run e2e        | yarn e2e        | ng e2e                                                          |
| i18n:extract | Extract i18n messages from i18n directives       | npm run extract    | yarn extract    | ng extract-i18n --output-path locale --ivy                      |
| analyze      | Open webpack-bundle-analyzer                     | npm run analyze    | yarn analyze    | webpack-bundle-analyzer dist/angular-boilerplate/stats.json     |
