# Railで悩んだ・引っかかった箇所をまとめる。
## formでユーザなど登録する際に特定のkeyが保存されない。
Strong parametersで指定した項目がtypoしていた。  

### 例
```Ruby
class UsersController < ApplicationController
  ...
  private
    def user_params
      params.require(:user).permit(:name, :email, :use_id) # user_idと記述するところをtypo
    end
end
```
