# Django

## 1. Django如何在数据库里面直接修改用户密码

问：我的管理员密码忘记了，怎么修改？

答：

> Django==1.10.5

```python
from django.contrib.auth.models import User


user = User.objects.filter(is_superuser=True).first()
user.set_password('new-password')
user.save()
```