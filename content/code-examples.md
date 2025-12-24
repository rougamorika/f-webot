---
title: 代码示例
date: 2025-12-24
tags:
  - 编程
  - 代码
  - 示例
---

# 代码示例

本页面展示 Quartz 的代码语法高亮功能，支持多种编程语言。

## Python 示例

```python
def fibonacci(n):
    """计算斐波那契数列的第 n 项"""
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# 打印前 10 个斐波那契数
for i in range(10):
    print(f"F({i}) = {fibonacci(i)}")
```

## JavaScript 示例

```javascript
// 快速排序算法
function quickSort(arr) {
  if (arr.length <= 1) return arr;

  const pivot = arr[Math.floor(arr.length / 2)];
  const left = arr.filter(x => x < pivot);
  const middle = arr.filter(x => x === pivot);
  const right = arr.filter(x => x > pivot);

  return [...quickSort(left), ...middle, ...quickSort(right)];
}

const numbers = [3, 6, 8, 10, 1, 2, 1];
console.log(quickSort(numbers));
```

## TypeScript 示例

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

class UserService {
  private users: User[] = [];

  addUser(user: User): void {
    this.users.push(user);
  }

  findUserById(id: number): User | undefined {
    return this.users.find(user => user.id === id);
  }
}
```

## Java 示例

```java
public class BinarySearch {
    public static int search(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }

        return -1;
    }
}
```

## 相关笔记

- [[math-formulas|数学公式示例]] - 查看数学公式渲染
- [[markdown-syntax|Markdown 语法]] - 学习 Markdown 基础
- [[index|返回首页]]
