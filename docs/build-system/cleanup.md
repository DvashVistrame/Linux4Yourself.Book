# Очистка системы

Во время тестов может создаваться большое количество временных файлов. Удалите их:

```bash
rm -rf /tmp/*
```

Перезайдите в среду `chroot`:

```bash
logout
```

<common-script :name="'chroot'"></common-script>

Файлы `.la` потеряли свою актуальность и могут вызвать проблемы при обновлении. Удалите их:

```bash
find /usr/lib /usr/libexec /usr/lib32 -name \*.la -delete
```

Удалите временный компилятор:

```bash
find /usr -depth -name $(uname -m)-lin-linux-gnu\* | xargs rm -rf
```

Удалите кросс-компилятор:

```bash
rm -rf /tools
```

Удалите созданного для тестов пользователя:

```bash
userdel -r tester
```

Вы можете удалить ненужные символы из исполняемых файлов:

```bash
find /usr/lib{,32} -type f -name \*.a \
   -exec strip --strip-debug {} ';'

find /usr/lib{,32} -type f -name \*.so* ! -name \*dbg \
   -exec strip --strip-unneeded {} ';'

find /usr/{bin,sbin,libexec} -type f \
    -exec strip --strip-all {} ';'
```

<script>
	new Vue({ el: '#main' })
</script> 
