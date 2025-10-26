# days_difference
Вычисляет разницу между двумя датами в днях (по модулю)
from datetime import datetime

def days_difference(date1_str, date2_str):
    """Вычисляет разницу между двумя датами в днях (по модулю)."""
    try:
        # Преобразуем строки в объекты datetime
        date1 = datetime.strptime(date1_str, "%Y-%m-%d")
        date2 = datetime.strptime(date2_str, "%Y-%m-%d")

        diff = (date2 - date1).days
        return abs(diff)

    except ValueError:
        print("Ошибка: неверный формат даты. Используйте формат ГГГГ-ММ-ДД (например: 2025-10-24).")
        return None


if __name__ == "__main__":
    # Ввод данных
    date1_input = input("Введите первую дату (в формате ГГГГ-ММ-ДД): ").strip()
    date2_input = input("Введите вторую дату (в формате ГГГГ-ММ-ДД): ").strip()
    result = days_difference(date1_input, date2_input)

    if result is not None:
        print(f"Разница между датами составляет {result} дней.")
