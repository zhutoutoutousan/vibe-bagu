---
title: Two Sum / 两数之和 / Zwei Summen / Somme de deux nombres / Suma de dos números
difficulty: Easy
tags: [Array, Hash Table, Algorithms, Top100]
languages: [zh, en, de, fr, es]
status: Active
created: 2024-03-20
lastUpdated: 2024-03-20
companies: [Amazon, Google, Microsoft]
---

## Description [en]
Given an array of integers `nums` and an integer `target`, return indices of the two numbers in the array such that they add up to `target`. You may assume that each input would have exactly one solution, and you may not use the same element twice.

## 题目描述 [zh]
给定一个整数数组 `nums` 和一个整数目标值 `target`，请你在该数组中找出和为目标值 `target` 的那两个整数，并返回它们的数组下标。你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

## Beschreibung [de]
Gegeben ist ein Array von ganzen Zahlen `nums` und eine ganze Zahl `target`. Geben Sie die Indizes der beiden Zahlen im Array zurück, die sich zu `target` addieren. Sie können davon ausgehen, dass jede Eingabe genau eine Lösung hat und Sie dasselbe Element nicht zweimal verwenden dürfen.

## Description [fr]
Étant donné un tableau d'entiers `nums` et un entier `target`, renvoyez les indices des deux nombres du tableau tels que leur somme soit égale à `target`. Vous pouvez supposer que chaque entrée aurait exactement une solution et vous ne pouvez pas utiliser le même élément deux fois.

## Descripción [es]
Dado un array de números enteros `nums` y un entero `target`, devuelve los índices de los dos números en el array tales que sumen `target`. Puedes asumir que cada entrada tendría exactamente una solución y no puedes usar el mismo elemento dos veces.

## Examples / 示例 / Beispiele / Exemples / Ejemplos

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: nums[0] + nums[1] = 2 + 7 = 9
```

## Solution Approach / 解题思路 / Lösungsansatz / Approche de solution / Enfoque de solución

### [en]
We can use a hash table to store the complement of each number we've seen so far. For each number, we check if its complement exists in the hash table. If it does, we've found our solution. If not, we add the current number to the hash table.

### [zh]
我们可以使用哈希表来存储已经遍历过的数字的补数。对于每个数字，我们检查它的补数是否存在于哈希表中。如果存在，我们就找到了解决方案。如果不存在，我们将当前数字添加到哈希表中。

### [de]
Wir können eine Hashtabelle verwenden, um die Komplemente der bisher gesehenen Zahlen zu speichern. Für jede Zahl prüfen wir, ob ihr Komplement in der Hashtabelle existiert. Wenn ja, haben wir unsere Lösung gefunden. Wenn nicht, fügen wir die aktuelle Zahl zur Hashtabelle hinzu.

### [fr]
Nous pouvons utiliser une table de hachage pour stocker le complément de chaque nombre que nous avons vu jusqu'à présent. Pour chaque nombre, nous vérifions si son complément existe dans la table de hachage. Si c'est le cas, nous avons trouvé notre solution. Sinon, nous ajoutons le nombre actuel à la table de hachage.

### [es]
Podemos usar una tabla hash para almacenar el complemento de cada número que hemos visto hasta ahora. Para cada número, comprobamos si su complemento existe en la tabla hash. Si existe, hemos encontrado nuestra solución. Si no, añadimos el número actual a la tabla hash.

## Implementations

### Python
```python
def twoSum(nums: List[int], target: int) -> List[int]:
    seen = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in seen:
            return [seen[complement], i]
        seen[num] = i
    return []
```

### Java
```java
public int[] twoSum(int[] nums, int target) {
    Map<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
        int complement = target - nums[i];
        if (map.containsKey(complement)) {
            return new int[] { map.get(complement), i };
        }
        map.put(nums[i], i);
    }
    return new int[0];
}
```

### JavaScript
```javascript
function twoSum(nums, target) {
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (map.has(complement)) {
            return [map.get(complement), i];
        }
        map.set(nums[i], i);
    }
    return [];
}
```

## Related Questions / 相关题目 / Verwandte Fragen / Questions connexes / Preguntas relacionadas
- Three Sum (Medium)
- Four Sum (Medium)
- Two Sum II - Input Array Is Sorted (Easy)

## Learning Resources / 学习资源 / Lernressourcen / Ressources d'apprentissage / Recursos de aprendizaje
- [Hash Table Tutorial](https://example.com/hash-table)
- [Array Data Structure](https://example.com/array)
- [Time Complexity Analysis](https://example.com/complexity) 