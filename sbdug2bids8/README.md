Buhat bago nga endpoint/route kung asa mag-request.

I-apil sa request ang information necessary, for example:

```
GET root/similar?top=20&sequence=ABSUGBQIUWBBSAJQWI
```
Or pwede sad POST request, kaw bahala

Kailangan custom viewset para mag-receive/process sa request

Dili na kaayo ko familiar, pero murag ani mahitabo:
```python
class SimilarViewSet(mixins.ListModelMixin):
  # ...
  def get_queryset(self):
    # use self.request to get request parameters
    # kuha tanan sequences sa DB
    # calculate similarity score for each
    # sort (plus filter top X similar if necessary)
    # return (and format) results
```

I search lang about custom filtering/sorting sa DRF
