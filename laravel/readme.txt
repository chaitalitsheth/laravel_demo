Laravel Install

composer create-project laravel/laravel laravel
cd laravel
php artisan serve
configure database in .env
php artisan migrate

composer require laravel/ui
php artisan ui vue --auth
php artisan ui:auth

php artisan ui bootstrap --auth
npm install


clear cache need to run following command
php artisan config:cache

You need to add following code in app/Http/Controller/Auth/RegisterController.php
'email' => ['required', 'string', 'email','regex:/(.*)@(gmail|yahoo|Hotmail)\.(com|co|in)/i', 'max:255', 'unique:users'],

For Verify email Following steps need to follow in laravel
=============================================================
1) routes/web.php
    verify must be true
    Auth::routes(['verify'=>true]);
2) go to app/Models/User.php
    add MustVerifyEmail must be implements in User Model
2) Go to app/Http/Controller/homecontroller.php
        add verified in middleware
        public function __construct()
            {
                $this->middleware(['auth','verified']);
            }




