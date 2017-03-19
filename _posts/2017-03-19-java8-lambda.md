---
layout: post
title:  "Java8 Lambda"
date:   2017-03-19 14:45:48 +0900
categories: java8 lambda
---
'java8 lambda' Sample

Code:
{% highlight ruby %}
public class Main {

    interface SayIt
    {
        void sayMsg(String msg);
    }

    public static void main(String[] args)
    {
        Testlambda lambda = new Testlambda();

        System.out.println("10 + 5 = " + lambda.addtion.operation(10,5));
        System.out.println("10 - 5 = " + lambda.subtraction.operation(10, 5));

        System.out.println("10 * 5 = " + lambda.operate(10,5, lambda.multiplation));
        System.out.println("10 / 5 = " + lambda.operate(10,5, lambda.division));

        System.out.println();

        SayIt toA = msg -> System.out.println("To A : " + msg);
        SayIt toB = msg -> System.out.println("to B : " + msg);

        toA.sayMsg("Hello");
        toB.sayMsg("Hello");

        System.out.println();
    }
}

class Testlambda
{
    interface MathOperation
    {
        int operation(int a, int b);
    }

    MathOperation addtion = (int a, int b) -> a + b;
    MathOperation subtraction = (int a, int b) -> a - b;
    MathOperation multiplation = (int a, int b) -> a * b;
    MathOperation division = (int a, int b) -> a / b;

    public int operate(int a, int b, MathOperation mathOperation)
    {
        return mathOperation.operation(a, b);
    }
}
{% endhighlight %}

Result:
{% highlight ruby %}
10 + 5 = 15
10 - 5 = 5
10 * 5 = 50
10 / 5 = 2

To A : Hello
to B : Hello
{% endhighlight %}

Check out the [tutorialspoint][tutorialspoint-docs] for more info.

[tutorialspoint-docs]: https://www.tutorialspoint.com/java8/java8_lambda_expressions.htm

