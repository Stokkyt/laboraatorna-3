```markdown
# Звіт з автоматизації тестування

### 📌 Мета
Навчитися налаштовувати CI/CD пайплайни за допомогою GitHub Actions для автоматичного тестування Python-коду.

---

## 🛠️ Виконання роботи

### 1. Базовий Workflow
- Використано шаблон "Python application"
- Додано кроки:
  ```yaml
  - name: Run main script
    run: python lab.py
  ```

### 2. Розширена конфігурація
- **Ручний запуск**:
  ```yaml
  on:
    workflow_dispatch
  ```
- **За розкладом** (щодня о 9:00):
  ```yaml
  schedule:
    - cron: '0 9 * * *'
  ```

### 3. Архітектура рішень
Створено 2 окремих workflow-файли:

| Файл          | Призначення                     | Візуалізація              |
|---------------|---------------------------------|--------------------------|
| `workflow1.yml` | Запуск основного скрипту        | ![Screenshot 1](photos/Screenshot_1.png) |
| `workflow2.yml` | Виконання тестів                | ![Screenshot 2](photos/Screenshot_2.png) |

### 4. Тестовий код
**Основна логіка** (`lab.py`):
```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

**Тести** (`test_lab.py`):
```python
def test_add():
    assert add(3, 5) == 8

def test_subtract():
    assert subtract(5, 3) == 2
```

---

## 📊 Результати
- Успішна інтеграція з Codecov
- Баджи статусів:
  [![Workflow 1](https://github.com/.../badge.svg)](https://github.com/...)
  [![Workflow 2](https://github.com/.../badge.svg)](https://github.com/...)

![Загальний вигляд](photos/Screenshot_7.png)

---

## 📌 Висновки
1. **Досягнення**: Реалізовано повний цикл CI/CD для Python-проєкту
2. **Складності**: Проблеми з віртуальним оточенням Ubuntu
3. **Перспективи**: Додати артефакти та релізи
4. **Оцінка**: 9/10 - потрібно більше прикладів з advanced features
