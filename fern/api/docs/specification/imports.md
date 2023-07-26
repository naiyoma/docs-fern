```yaml person.yml
types:
  Person: ...
```

```yaml family.yml
imports:
  person: ./path/to/person.yml
types:
  Family:
    properties:
      people: list<person.Person> # use an imported type
```

Note that you can only import files that exist in your Fern specification (i.e., in the same `definition/` folder).
