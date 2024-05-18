```mermaid
graph TD
    A[Start] --> B[Input c]
    B --> C{c != '\n'?}
    C -- Yes --> D{c == 'z'?}
    D -- Yes --> E[c = '*']
    E --> F[Output c]
    D -- No --> G{c >= 'A'?}
    G -- Yes --> H[c++]
    H --> F
    G -- No --> F
    F --> I[Input next c]
    I --> C
    C -- No --> J[End]

```

```c
cin.get(c);
while (C != '\n')     // 从标准输入读取第一个字符并将其存储在变量c中。
{
  if (c == 'z')
  {
    c = '*';
  }
  else if (c >= 'A')
  {
    c++;
  }
  cout << c; // 将变换后的字符c打印到标准输出
  cin.get(c); // 从标准输入读取下一个字符，存储在c中，循环继续，直到遇到换行符
}
```







```mermaid
graph TD
    A[Start: Input c] -->|read c| B{c == '\n'?}
    B -- No --> C{c == 'z'?}
    C -- Yes --> D[c = '*']
    C -- No --> E{c >= 'A'?}
    E -- Yes --> F[c++]
    E -- No --> G[Output c without change]
    D --> H[Output modified c]
    F --> H
    H --> I[Input next c]
    I --> B
    B -- Yes --> J[End]
```





```mermaid
graph TD;
    a --> sum;
    b --> sum;
    a --> product;
    b --> product;
    b --> difference;
    a --> difference;
    sum --> result;
    product --> result;
    difference --> result;


```



```java
public class ArraySumAndAverage {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int sum = 0;
        double average = 0.0;
        
        for(int i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        
        average = sum / numbers.length;
        
        System.out.println("Sum = " + sum);
        System.out.println("Average = " + average);
    }
}

```





```mermaid
graph TD;
    numbers --> sum;
    sum --> average;
    sum --> sum[sum+numbers i];

```



```mermaid
graph TD;
    numbers --> evenSum;
    numbers --> evenCount;
    evenSum --> evenAverage;
    evenCount --> evenAverage;

    subgraph loop["for (int i = 0; i < numbers.length; i++)"]
        numbers -->|read in loop| evenSum;
        numbers -->|read in loop| evenCount;
    end

    subgraph condition["if (numbers[i] % 2 == 0)"]
        numbers -->|condition for| evenSum;
        numbers -->|condition for| evenCount;
    end

    subgraph ifCondition["if (evenCount > 0)"]
        evenSum -->|used in condition| evenAverage;
        evenCount -->|condition| evenAverage;
    end

```



```mermaid
graph TD;
    a --> sum;
    b --> sum;
    a --> product;
    b --> product;
    b --> difference;
    a --> difference;
    sum --> result;
    product --> result;
    difference --> result;

```

