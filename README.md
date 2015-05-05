# Full word filter backend for django REST framework

Database independent (runs without regexp), easy to use full word search backend.
Do not use with default ``filters.SearchFilter`

## Install

    pip install django-rest-framework-word-search-filter

In your ``settings.py``

    INSTALLED_APPD += ('rest_framework_word_filter', )

## Using

Import

    from rest_framework_word_filter import FullWordSearchFilter
    ....
    
and add to filter backends. Add attribute ``word_fields`` to define which fields in model will be used for search.

    class FooListView(ListAPIView):
        model = Foo
        queryset = Foo.objects.all()
        serializer_class = FooSerializer
        filter_backends = (FullWordSearchFilter, )
        word_fields = ('text',)

This is my first package, if you find mistake - write me, or send pull-request =)

