template-gen-qr
===============
Projeto de templatetag Django para geração de Qr Codes em base64

required: https://github.com/lincolnloop/python-qrcode

Usando em Templates
-------------------

```html
  {% load qr_tags %}
  {% qr_from_mail 'zokis@example.com' %}
  {% qr_from_text 'Texto!!' %}
```
Usando o MECARD:
```python

def gen_qr(request):
  contato = {
              'url': 'http://www.znc.com.br',
              'tel': '000666',
              'name': 'Marcelo Tambalo',
              'email': 'zokis@example.com',
              'nick': 'Zokis'
            }
  return render(request, 'app/template.html', {'contato': contato})
```
```html
  {% load qr_tags %}
  {% qr_from_contact contato %}
```
