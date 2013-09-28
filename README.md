Rails' Second-Step
==================

搞懂CRUD後該懂的架站技巧及實務

## 會員機制

### [Devise]() -  
  這個套件幾乎收集了會員系統所需要的所有功能，從最基本的登入、註冊、忘記密碼、認證信...等等。  
  相關介紹請參見ihower的「[Ruby on Rails 實戰聖經](http://ihower.tw/rails3/auth.html)」
  
### [Omniauth]() - 
  這個套件專門用來處理第三方登入的管理，如facebook, twitter, github等多個provider的登入整合。
  相關介紹請參見xdite的「[OmniAuth - 實作多方認證的最佳實踐](http://blog.xdite.net/posts/2011/11/19/omniauth-clean-auth-provider-1/)」
  
### [CANCAN]() -
  這個套件可以用來對使用者的權限做控管
  相關介紹請參見xdite的「[Cancan 實作角色權限設計的最佳實踐](http://blog.xdite.net/posts/2012/07/30/cancan-rule-engine-authorization-based-library-1)」
  
  
## 後台

### [ActiveAdmin](http://www.activeadmin.info/) -
  
### [rails_admin](https://github.com/sferik/rails_admin) - 
  
  
## 除錯及效能監控

### [Better_Errors](https://github.com/charliesome/better_errors) - 
  這個套件能讓你更清楚的trace error_log及其所在的程式碼區段，使用方式很簡單不多做介紹。
  只是需要提醒的是，這種在開發環境下才使用的套件要放在Gemfile的developement scope中：
  ```
  group :development do
    gem "better_errors"
  end
  ```

### [Miniprofoler](http://miniprofiler.com/) - 
  這是個不可多得必裝的套件，尤其是新手。安裝他後能在頁面的角落顯示render這個頁面過程中所耗的運算時間，如render頁面或db-query等task。
  有了他就更容易去調校網站的校能。一樣只需要裝在developement mode下  
  
### Airbrake - 
  在production下發生error時，會將error log記錄在Airbrake的系統後台，並同時寄送一封信到註冊的email信箱。非常實用。但是一樣推薦安裝在production scope中。
  
  
  

## Worker & 排程

### [Delayed_job](https://github.com/collectiveidea/delayed_job)

### [Resque](https://github.com/resque/resque)

### [Sidekiq](https://github.com/mperham/sidekiq)

以上三個套件的比較可以參考：https://github.com/mperham/sidekiq/wiki/FAQ

### [devise-async](https://github.com/mhfs/devise-async)
  
### [Whenever](https://github.com/javan/whenever)
  
  
  
## 前端編程效率

### Slim

### SASS

### Campass

### Coffee_Script
  
  
  
