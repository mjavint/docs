# Acceso al Entorno de Odoo (Environment)

The object `self.env` gives access to request parameters and other useful things:

- `self.env.cr` or `self._cr` is the database cursor object; it is used for querying the database
- `self.env.uid` or `self._uid` is the current user’s database id
- `self.env.user` is the current user’s record
- `self.env.context` or `self._context` is the context dictionary
- `self.env.ref(xml_id)` returns the record corresponding to an XML id
- `self.env[model_name]` returns an instance of the given model
