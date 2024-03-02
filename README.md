1. **Подготовка ингредиентов:**
   - Очистите картофель от кожуры.
   - Натрите картофель на терке средней или крупной терки.
   - Если желаете, добавьте в тесто мелко нарезанный лук или другие ингредиенты по вашему вкусу.

2. **Выжимание лишней влаги:**
   - Выложите натертый картофель на чистую ткань или марлю.
   - Сверните ткань в пакет и тщательно выжмите лишнюю влагу из картофеля.
   - Этот шаг поможет драникам лучше держать форму и обеспечит им хрустящую корочку.

3. **Приготовление теста:**
   - Переложите выжатый картофель в большую миску.
   - Добавьте соль и перец по вкусу.
   - Если используете, добавьте яйцо для связки.
   - Тщательно перемешайте, чтобы ингредиенты равномерно смешались.

4. **Формирование драников:**
   - Нагрейте сковороду с растительным маслом на среднем огне.
   - Выложите порцию теста на сковороду и разровняйте, чтобы образовать круглую или овальную форму.
   - Жарьте драники с каждой стороны до золотистой корочки и готовности внутри.

5. **Подача и подача:**
   - Подавайте драники горячими, с кислородом сметаной, тертым сыром или зеленью по вашему выбору.
   - Наслаждайтесь этим традиционным блюдом вместе с вашей семьей и друзьями!

![Кот](https://media.discordapp.net/attachments/819988997107089469/1213594875077988473/image.png?ex=65f60b4d&is=65e3964d&hm=c137b849e93606bc6285f26655124da3afab1d881b0805b071de817eda1a61c3&=&format=webp&quality=lossless&width=526&height=700)

---

```python
class CoordinateHistoryViewSet(ModelViewSet):
    queryset = CoordinateHistory.objects.all()
    serializer_class = CoordinateHistorySerializer
    transport_lookup_field = "transport_name"

    def get_queryset(self):
        return super().get_queryset().filter(transport__name=self.kwargs[self.transport_lookup_field])

    def perform_create(self, serializer: CoordinateHistorySerializer) -> None:
        transport = get_object_or_404(Transport, name=self.kwargs[self.transport_lookup_field])
        serializer.save(transport=transport)
```

- Первый абзац текста. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus hendrerit, elit sit amet sagittis posuere, mauris justo bibendum magna, ut commodo nulla libero nec ante.
- Второй абзац текста. Duis posuere felis sed nulla accumsan, non volutpat risus vehicula. Nulla facilisi. Fusce lobortis eros a vestibulum viverra.
- Третий абзац текста. Sed nec ligula nec lectus tincidunt euismod. Quisque vulputate tortor at turpis fermentum, sit amet dapibus odio cursus.
- Четвертый абзац текста. Phasellus eget erat id ex bibendum dapibus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nullam vel nisi sit amet velit condimentum consequat.


## Структура
- apps - приложения
- config - настройки
- файлы в корне - конфигурационные файлы


## Установка приложения

Сначала убедитесь, что у вас установлен python3.11 на вашем компьютере. Если нет, вы можете скачать и установить Docker с [официального сайта Docker](https://www.docker.com/get-started).

Сделайте виртуальную среду:
```bash
python -m venv venv
```

Активируйте его:
```bash
source first_venv/bin/activate
```

Установите пакеты:
```bash
pip install -r requirements.txt 
```

## Запуск приложения
Для запуска используйте следующую команду:
```bash
python manage.py runserver
```
