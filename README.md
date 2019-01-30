# Rails Bind Privileges

Attach user privileges to Rails' controller actions

## Example
```ruby
class FoobarController < ApplicationController
  include RailsBindPrivileges

  # Will limit create action to users having a role with
  # 'Create foobar'  privilege
  bind_privilege 'Create foobar', %i[create]

  def create
    render json: { data: 'Foobar created' }, status: :created
  end
end
```