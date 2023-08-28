# Tipos de Herencia

## Herencia Tradicional

### Herencia de Clase

Cuando queremos extender el Modelo

```py
Class ResCompany(models.Model):
    _name = ‘res.company’
    company_type
```

```py
Class ResCompany(models.Model)
    _name = ‘res.company’
    _inherit = ‘res.company’

    code
```

Nota: No es necesario poner `_name` cuando sea igual a `_inherit`

```py
Class ResCompany(models.Model)
    _inherit = ‘res.company’

    code
```

———————————————————————

### Herencia Prototipo

Cuando queremos copiar la estructura de campos en un nuevo modelo y personalizarlos

```py
Class ResCompany(models.Model)
    _name = ‘res.company’

    company_type
```

```py
Class ResCompany(models.Model)
    _name = ‘res.company.prueba’
    _inherit = ‘res.company’

    code
```

———————————————————————

## Herencia por Delegación

Cuando queremos copiar los campos y funciones de un modelo en uno nuevo agregando nuevas funcionalidades, pero si cambian los modelos heredados también cambia en la nueva clase Heredada

```py
Class AccountJournal(models.Model)
    _name = ‘account.journal’
    _inherit = [‘mail.thread’, ‘mail.activity.mixin’]
```
