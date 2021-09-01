### 마이그레이션 초기화

```shell
python manage.py migrate --fake blog zero
```

### Customize ManyToManyModel Manager

```python
""" Manger말고 BaseManger로 하면 안됨! """
class ManyToManyModelManager(Manager.from_queryset(ManyToManyModelQuerySet)):
    pass
```
