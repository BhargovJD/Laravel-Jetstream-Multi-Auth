1.  composer require laravel/jetstream
2.  php artisan jetstream:install livewire
3.  npm install
4.  npm run dev
5.  Go to migration folder->Crete user migration->add a filed(role) with default value 0
6.  Set up database in .env file
7.  php artisan migrate
8.  Refresh page
9.  Create 2 account as User and Admin
10. Inside user table make role value of admin to 1
11. Go to App\Providers\RouteServiceProviders.php and Chnage its home route to '/divider'
12. Create home controller: php artisan make:controller HomeController
    public function index(){

        $role=Auth::user()->role;

        if($role==1){
            return view('admin.dashboard');
        }
        else{
            return view('user.dashboard');
        }

    }

13. Create Admin/dashboard.blade.php and User/dashboard.blade.php
14. Route::get('/divider', [HomeController::class,'index']);
