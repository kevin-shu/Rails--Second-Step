Rails' Second-Step
==================

搞懂CRUD後該懂的架站技巧及實務

## 會員機制

### [Devise](https://github.com/plataformatec/devise) -  
  這個套件幾乎收集了會員系統所需要的所有功能，從最基本的登入、註冊、忘記密碼、認證信...等等。  
  相關介紹請參見ihower的「[Ruby on Rails 實戰聖經](http://ihower.tw/rails3/auth.html)」
  
### [Omniauth](https://github.com/intridea/omniauth) - 
  這個套件專門用來處理第三方登入的管理，如facebook, twitter, github等多個provider的登入整合。
  相關介紹請參見xdite的「[OmniAuth - 實作多方認證的最佳實踐](http://blog.xdite.net/posts/2011/11/19/omniauth-clean-auth-provider-1/)」
  
### [CANCAN](https://github.com/ryanb/cancan) -
  這個套件可以用來對使用者的權限做控管
  相關介紹請參見xdite的「[Cancan 實作角色權限設計的最佳實踐](http://blog.xdite.net/posts/2012/07/30/cancan-rule-engine-authorization-based-library-1)」
  
  
## 後台

  以下兩個後台套件能讓你馬上產生一個後台系統，在系統開發初期或小型的專案其實夠用了。

### [ActiveAdmin](http://www.activeadmin.info/) -
  
### [rails_admin](https://github.com/sferik/rails_admin) - 
  比起ActiveAdmin，這個套件的客製化彈性較高。
  
  
  
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
  
### [Airbrake](https://github.com/airbrake/airbrake) - 
  在production下發生error時，會將error log記錄在Airbrake的系統後台，並同時寄送一封信到註冊的email信箱。非常實用。但是一樣推薦安裝在production scope中。
  
  

## Worker & 排程

  Delayed_job、Resque、Sidekiq都是非同步多工執行套件，原理是將預期會做很久的工作(如寄送email)丟到一個task queue裡，由事先開好的worker在背景執行他。
  這樣的好處是可以避免因為web application因為處理這件事情花了太多時間而阻斷了其他user的access。

### [Delayed_job](https://github.com/collectiveidea/delayed_job)
  這個非同步執行套件是使用SQL來做task queue的儲存，安裝簡單。

### [Resque](https://github.com/resque/resque)
  這個套件是使用Redis來做task queue的管理，效能好上不少，但是設定麻煩。

### [Sidekiq](https://github.com/mperham/sidekiq)
  Sidekiq其實跟Resque很像，只是他在建置多個worker時是使用multi-thread，而不像Reque一樣每一個worker都是一個process，比較浪費記憶體空間。
  所以整體來說Sidekiq的效能會最好。

以上三個套件的比較可以參考：https://github.com/mperham/sidekiq/wiki/FAQ

### [devise-async](https://github.com/mhfs/devise-async)
  
### [Whenever](https://github.com/javan/whenever)
  
  
  
## 前端編程效率

### Slim
  讓html寫起來更快速，非常推薦使用

### SASS

### Compass
  Compass跟SASS的關係可以想像成jQuery跟javascript，能讓你的sass寫起來更快速。  
  尤其是在處理css3跨瀏覽器的對應屬性不同的問題更是方便。

### Coffee_Script
  
  
  
## 系統安全、備份

### [Backup](https://github.com/meskyanichi/backup)
  幫你的SQL做備份，可搭配「Whenever」做定期備份機制。  
  可以參考黃金俠的「[用 backup gem 做自動化備份](http://rubyist.marsz.tw/blog/2012-03-08/backup-gem/)」

### [Brakeman](https://github.com/presidentbeef/brakeman)
  掃描你專案中的安全性弱點

### [Rails SQL Injection](http://rails-sqli.org/)
  這不是套件，是一個網站，上面整理了Rails專案中最常遇到的SQL injection問題


## Document

### [Rails-ERD](https://github.com/voormedia/rails-erd)
  這個套件可以幫你自動化產出 UML 圖形，原理是找所有的 model 檔並依 relation 找到彼此關係。  
  順帶一提，它也能檢查你的系統的 relation 有沒有錯誤。
