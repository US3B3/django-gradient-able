# [Gradient Able Django](https://appseed.us/admin-dashboards/django-gradient-able)
# [TÜRKÇE](https://muhammedy.com/)

Açık kaynak kodlu **[Django Dashboard](https://appseed.us/admin-dashboards/django)** [AppSeed](https://github.com/app-generator/django-gradient-able) tarafından oluşturulan Gradient Able Django temasını Türkçeleştirme çalışması. **[Gradient Able](https://appseed.us/admin-dashboards/django-gradient-able)** Bootstrap 4 Ücretsiz/Lite Yönetici Şablonu, pano oluşturmanız için eksiksiz bir çözümdür. Gradient Able, yumuşak degrade renkleri çok uygun tipografi ve harika kartlar ve grafiklerle birleştiren zarif bir görünümle kalabalığın arasından sıyrılıyor. 

<br />

> Özellikler

- 'Güncel bağımlılıklar': **Django 3.2.6 LTS**
- UI-Ready uygulaması, SQLite Veritabanı, Django Native ORM
- Modüler tasarım, temiz kod tabanı
- Oturum Tabanlı Kimlik Doğrulama, Form doğrulama
- `Deployment`: **Docker**, Gunicorn / Nginx
- Beni destekleme için **Github** ve [muhammedy.com](https://muhammedy.com) adresini ve..
- [Appseed]'i desteklemek için **Github** and [Discord](https://discord.gg/fZC6hup) adreslerini ziyaret edebilirsiniz.

<br />

> Links

- [Gradient Able Django](https://appseed.us/admin-dashboards/django-gradient-able) - Ürün sayfası(İng)
- [Gradient Able Django](https://django-gradient-able.appseed-srv1.com/) - Canlı Demo(İng)

<br />

## Hızlı Başlangıç [Docker](https://www.docker.com/)

> Kodu alın

```bash
$ git clone https://github.com/app-generator/django-gradient-able.git
$ cd django-gradient-able
```

> Uygulamayı Docker ile başlatın

```bash
$ docker-compose up --build
```

`http://localhost:85` adresine tarayıcınızda gidin. Uygulama çalışıyor olacak

<br />

![Django Dashboard GradientAble - AppSeed tarafından sağlanan Açık Kaynak şablon projesi.](https://raw.githubusercontent.com/app-generator/django-dashboard-gradientable/master/media/django-dashboard-gradientable-screen.png)

<br />

## Nasıl kullanılır

```bash
$ # Kodu alın
$ git clone https://github.com/app-generator/django-gradient-able.git
$ cd django-gradient-able
$
$ # Virtualenv modüllerini yükleyin (Unix tabanlı sistemler[Linux, MacOS vs.])
$ virtualenv env
$ source env/bin/activate
$
$ # Virtualenv modüllerini yükleyin (Windows tabanlı sistemler)
$ # virtualenv env
$ # .\env\Scripts\activate
$
$ # Install modules - SQLite Storage
$ pip3 install -r requirements.txt
$
$ # Tabloları oluşturun
$ python manage.py makemigrations
$ python manage.py migrate
$
$ # Uygulamayı başlatın (geliştirici modu)
$ python manage.py runserver # varsayılan port 8000
$
$ # Uygulamayı başlatın - özel port
$ # python manage.py runserver 0.0.0.0:<your_port>
$
$ # Tarayıcınız ile uygulamaya gidin: http://127.0.0.1:8000/
```

> Not: Uygulamayı kullanmak için lütfen kayıt sayfasına erişin ve yeni bir kullanıcı oluşturun. Kimlik doğrulamadan sonra, uygulama özel sayfaların kilidini açacaktır.

<br />

## Kod tabanlı yapı

Proje, aşağıda sunulan basit ve sezgisel bir yapı kullanılarak kodlanmıştır:

```bash
< PROJE KÖKÜ>
   |
   |-- core/                               # Uygulama mantığını uygular ve statik varlıklara hizmet eder
   |    |-- settings.py                    # Django uygulaması önyükleyici
   |    |-- wsgi.py                        # Uygulamayı üretimde başlatın
   |    |-- urls.py                        # Tüm apps/nodes tarafından sunulan URL'leri tanımlayın
   |    |
   |    |-- static/
   |    |    |-- <css, JS, images>         # CSS dosyaları, Javascripts dosyaları
   |    |
   |    |-- templates/                     # Sayfaları oluşturmak için kullanılan şablonlar
   |         |
   |         |-- includes/                 # HTML parçaları ve bileşenleri
   |         |    |-- navigation.html      # Üst menü bileşeni
   |         |    |-- sidebar.html         # Kenar çubuğu bileşeni
   |         |    |-- footer.html          # Uygulama Altbilgisi
   |         |    |-- scripts.html         # Tüm sayfalar için ortak komut dosyaları
   |         |
   |         |-- layouts/                  # Ana sayfalar
   |         |    |-- base-fullscreen.html # Kimlik doğrulama sayfaları tarafından kullanılır
   |         |    |-- base.html            # Ortak sayfalar tarafından kullanılır
   |         |
   |         |-- accounts/                 # Kimlik doğrulama sayfaları
   |         |    |-- login.html           # Giriş sayfası
   |         |    |-- register.html        # Kayıt sayfası
   |         |
   |      index.html                       # Varsayılan sayfa
   |     page-404.html                     # Hata 404 sayfası
   |     page-500.html                     # Hata 500 sayfası
   |       *.html                          # Diğer tüm HTML sayfaları
   |
   |-- apps/
   |    |-- authentication/                # Yetkilendirme yollarını yönetir (oturum açma ve kayıt olma)
   |    |    |
   |    |    |-- urls.py                   # Kimlik doğrulama yollarını tanımlayın  
   |    |    |-- views.py                  # Giriş ve kayıt işlemlerini yürütür  
   |    |    |-- forms.py                  # Kimlik doğrulama formlarını tanımlayın  
   |    |
   |    |-- app/                           # HTML dosyaları sunan basit bir uygulama
   |         |
   |         |-- views.py                  # Kimliği doğrulanmış kullanıcılar için HTML sayfaları sunun
   |         |-- urls.py                   # Bazı süper basit rotalar tanımlayın 
   |
   |-- requirements.txt                    # Geliştirme modülleri - SQLite depolama
   |
   |-- .env                                # Ortam Yoluyla Yapılandırmayı Enjekte Et
   |-- manage.py                           # Uygulamayı başlatın - Django varsayılan başlatma komut dosyası
   |
   |-- ************************************************************************
```

<br />

> Önyükleme akışı

- Django önyükleyici "manage.py", ana yapılandırma dosyası olarak "core/settings.py"yi kullanır
- "core/settings.py", uygulama büyüsünü ".env" dosyasından yükler
- Konuk kullanıcıları Giriş sayfasına yönlendirin
- Kimliği doğrulanmış kullanıcılar için *app* düğümü tarafından sunulan sayfaların kilidini açın

<br />

## Dağıtım (Deployment)

Uygulama Docker içinden yürütülecek temel bir yapılandırma ile [Docker](https://www.docker.com/), [Gunicorn](https://gunicorn.org/), ve [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/) ayağa kalkar.

### [Docker](https://www.docker.com/) uygulaması
---

Uygulama bir liman işçisi kapsayıcısında kolayca yürütülebilir. Adımlar:

> Kodu alın

```bash
$ git clone https://github.com/app-generator/django-gradient-able.git
$ cd django-gradient-able
```

> Uygulamayı Docker'da başlatın

```bash
$ sudo docker-compose pull && sudo docker-compose build && sudo docker-compose up -d
```

`http://localhost:85` adresini tarayıcınızda açın. Uygulama çalışıyor olacaktır.

<br />

### [Gunicorn](https://gunicorn.org/)
---

Gunicorn 'Green Unicorn' UNIX için bir Python WSGI HTTP Sunucusudur.

> pip ile yükleyin

```bash
$ pip install gunicorn
```
> Uygulamayı gunicorn binary ile başlatın

```bash
$ gunicorn --bind=0.0.0.0:8001 core.wsgi:application
Serving on http://localhost:8001
```

`http://localhost:8001`adresini tarayıcınzda açın. Uygulama çalışıyor olacaktır.


<br />

### [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/)
---

Waitress (Windows için Gunicorn eşdeğeri), çok kabul edilebilir performansa sahip, üretim kalitesinde saf Python WSGI sunucusu anlamına gelir. Python standart kitaplığında yaşayanlar dışında hiçbir bağımlılığı yoktur.

> pip ile yükleyin

```bash
$ pip install waitress
```
> Uygulamayı [waitress-serve](https://docs.pylonsproject.org/projects/waitress/en/stable/runner.html) ile başlatın

```bash
$ waitress-serve --port=8001 core.wsgi:application
Serving on http://localhost:8001
```

`http://localhost:8001` adresini tarayıcınızda açın. Uygulama çalışıyor olacaktır.

<br />

## Bağlantılar

- [muhammedy.com](https://muhammedy.com) - Kişisel web sitem
- [Django](https://www.djangoproject.com/) - Django web sitesi
- [Boilerplate Code](https://appseed.us/boilerplate-code) - **AppSeed** tarafından sağlanan dizin
- [Boilerplate Code](https://github.com/app-generator/boilerplate-code) - Github'da yayınlanan dizin

<br />

---
[muhammedy.com](https://muhammedy.com) - Bu çalışma Muhammed Yıldırım (US3B3) **Github** tarafından yapılmıştır. 
<br />
[Gradient Able Django](https://appseed.us/admin-dashboards/django-gradient-able) - Provided by **AppSeed [App Generator](https://appseed.us/app-generator)**.
