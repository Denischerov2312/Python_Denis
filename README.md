# Вариант 66 (Medium задача с 71 варианта)

Репозиторий с решениями задач с LeetCode.

---
## 1. [804. Unique Morse Code Words](https://leetcode.com/problems/unique-morse-code-words/)
* **Сложность:** Easy
<img width="1048" height="527" alt="image" src="https://github.com/user-attachments/assets/30502031-a33b-48d3-a698-cd6ce1551922" />

### Решение
Используем `ord(lett) - 97` для вычисления смещения символа в массиве. Перед добавлением в итоговый массив, проверяем на уникальность
Ответ это размер этого списка.

### Код
```python
class Solution:
    def uniqueMorseRepresentations(self, words):
        itog = []
        alhpabet = [".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
        for word in words:
            parts = []
            for letter in word:
                code = alhpabet[ord(letter) - 97]
            parts.append(code)
            morse_word = "".join(parts)
            if morse_word not in itog:
                itog.append(morse_word)
            else: pass
        return len(itog)

```

## 2. [1047. Remove All Adjacent Duplicates In String](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/)

* **Сложность:** Easy
<img width="1048" height="521" alt="image" src="https://github.com/user-attachments/assets/b67b0228-6e82-49e4-ba5b-4ece8516c7bd" />

### Решение
Используем два указателя, последовательно идём по строке, сравнивая соседние символы, новые буквы записываются поверх старых дубликатов по текущему значению i
### Код
```python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        itog, i = list(s), 0
        for lett in s:
            itog[i] = lett
            if itog[i] == itog[i - 1] and i != 0:
                i -= 2
            i += 1
        return ''.join(itog[:i])

```

---
