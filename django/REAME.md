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

### paginator ordering

- drf cursor paginator는 \_\_ 룩업 필드를 지원하지 않는다.
- 따라서, F표현식을 통해 annotate한 후 ordering 하자

### multiple annotate bug

- 해당 aggregate에 `distinct=True`를 넣어주자!
- [관련자료](https://docs.djangoproject.com/en/3.2/topics/db/aggregation/#combining-multiple-aggregations)
