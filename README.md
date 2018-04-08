# ASP.Net-2
**Програмне забезпечення:**
 - Visual Studio Code: https://code.visualstudio.com
 - Heroku CLI: https://devcenter.heroku.com/articles/heroku-cli
 - Git: https://git-scm.com
 
Я зараз використовую Heroku.com як хостинг. Поки що не знайшов йому конкурента серед безкоштовних.
Там можна не тільки на asp.net core 2.0 проекти викладати, а є і підтримка nodejs, php, ruby і багато чого іншого. + все базується на git, а це зручно. Є ще безкоштовні періоди від google, redhat та amazon, але вони значно поступаються heroku у простоті використання та у обмеженнях на безкоштовному тариф. плані.

1. Відкриваємо visual studio code і створимо новий проект. Для цього у консолі вводимо $ **dotnet new webapi**, web-api - найбільш оптимальний шаблон. У empty потрібно багато додавати, а у mvc прибирати.

![Alt Text](https://github.com/licurg/ASP.Net-2/blob/master/gifs/3.gif)

2. Створимо у початковій директорії файл **app.json**. У ньому зберігається інформація про проект для heroku. Нам потрібно додати інформацію про buildpacks.

**app.json:**
```json
{
 "buildpacks": [
  {
   "url": "https://github.com/jincod/dotnetcore-buildpack"
  }
 ]
}
```

3. Після регістрації на heroku.com, заходимо у "dashboard". Далі потрібно створити новий проект.

![Alt Text](https://github.com/licurg/ASP.Net-2/blob/master/gifs/1.gif)

4. Переходимо у вкладку Settings в нашому проекті. Тут нам потрібно додати buildpacks. В heroku немає стандартного buildpack для asp.net core, тому потрібно його дотати зі сторони. Цих зборок багато, я використовую: https://github.com/jincod/dotnetcore-buildpack.

![Alt Text](https://github.com/licurg/ASP.Net-2/blob/master/gifs/2.gif)

5. Тепер потрібно завантажити наш проект з комп'ютера на сервер. Повертаємось в консоль.
 - Авторизуємось у HerokuCLI: $ **heroku login**.
 - Ініціалізуємо git у директорію: $ **git init**.
 - Підключаємось до проекту: $ **heroku git:remote -a PROJECT_NAME**. PROJECT_NAME - назва проекту.
 - Додаємо файли: $ **git add .**
 - Робимо commit: $ **git commit -am "commit"**.
 - Завантажуємо все на heroku: $ **git push heroku master**. 

Далі, коли щось змінюєте у проекті повторюєте три останні пункти.

![Alt Text](https://github.com/licurg/ASP.Net-2/blob/master/gifs/4.gif)
