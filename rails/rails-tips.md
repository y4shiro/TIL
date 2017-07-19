# Railsで悩んだ・引っかかった箇所をまとめる
## formでユーザなど登録する際に特定のkeyが保存されない
Strong parametersで指定した項目がtypoしていた。  
デフォだと許可されていないパラメータが渡されても怒られないので、  
`config/application.rb`で例外を発生させる動作に変更できる。  

### 例
```Ruby
class UsersController < ApplicationController
  ...
  def create
    @user = User.new(user_params)
  end
  ...
  private
    def user_params
      params.require(:user).permit(:name, :email, :use_id) # user_idと記述するところをtypo
    end
end
```
