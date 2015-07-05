# Rails Application Template

建立 rails 專案時的初始樣板。使用 bower 作為前端套件的管理工具，因此系統必須事先安裝 node.js 與 bower。

## 使用方法

建議將這個 repo 複製到使用者目錄底下

```sh
cd ~
git clone [url_of_this_repo]
```

在新建 rails 專案時使用 -m 指定這個 template

```sh
rails new example -m ~/Q-rails-application-template/qstyle.rb
```

## Gems

### 開發工具

```rb
# RSpec
gem "rspec-rails"
gem "shoulda-matchers"
gem "spring-commands-rspec"

# Capybara 整合測試
gem "capybara"
gem "capybara-screenshot"

# 使用 Guard 將開發流程的雜事自動化
gem 'guard-livereload'
gem 'guard-rspec', require: false
gem 'guard-pow'

# 可在 model 檔案中註釋 schema
gem 'annotate'

# 增強錯誤畫面
gem "better_errors"

# 支援 chrome 的 rails panel
gem "meta_request"

# 移除 log 中不必要的部份
gem "quiet_assets"

# 取代 fixture 來製作假資料
gem "factory_girl_rails"
gem "database_cleaner"

# coding style 建議
gem "rubocop"

# 偵測 N+1 問題
gem 'bullet'

# Deploy 工具
gem 'capistrano', '~> 3.1.0'
gem 'capistrano-bundler', '~> 1.1.2'
gem 'capistrano-rails', '~> 1.1.1'
gem 'capistrano-rbenv', github: "capistrano/rbenv"
```

### Rails 功能

```rb
# 使用者系統
gem "devise"

# Debug 工具
gem 'awesome_rails_console'

# flash message
gem 'growlyflash', '0.6.2'

# App settings function
gem "rails-settings-cached", "0.4.1"

# 分離敏感內容
gem 'settingslogic'

# for View components and cache
gem 'cells', "~> 4.0.0.beta2"

# 檔案上傳與影像處理
gem 'carrierwave'
gem 'mini_magick'
```

#### 可選功能

```rb
# API 開發工具組
if yes?("是否進行開發 API？ (yes/no)")

  # 資料序列化工具（JSON）
  gem "active_model_serializers"

  # API 開發工具
  gem "grape"
  gem "grape-active_model_serializers"
  gem "grape-swagger-rails"

  # 支援跨站請求
  gem "rack-cors", require: "rack/cors"
end

if yes?("是否使用 Facebook oauth 登入 (yes/no)")
  gem "omniauth"
  gem "omniauth-facebook"
end
```

### 前端

```rb
# 使用 compass
gem 'sprockets-rails'
gem 'sass-rails', '5.0.1'
gem 'compass-rails', '2.0.4'

# bootstrap
gem 'bootstrap-sass'

# font awesome
gem 'font-awesome-sass'

# 使用 bower 管理前端套件
gem 'bower-rails'

# modernizr
gem 'modernizr-rails'
```

#### 可選功能

```rb
if yes?('是否使用 React.js？（yes/no）')
  gem 'react-rails', '~> 1.0'
  gem 'sprockets-coffee-react'
end
```