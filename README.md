# Coding Bad - Arijit's Engineering Thread 


#### Do checkout my curated:
- [Must Check Engineering Explainers 🚀](https://www.notion.so/itsarijitray/Must-Check-Engineering-Explainers-1108347ee97180229187f0665785e76b)
- [Papershelf](papershelf.md)
- [Blogs](blogs.md)
- [Videos](videos.md)



## Threads by date:
- August 25, 2024: [Did you know that you can optimize memory by changing the order of struct fields in Go?](#did-you-know-that-you-can-optimize-memory-by-changing-the-order-of-struct-fields-in-go)
- May 11, 2024 : ["1000.01"*1 is faster than Number("1000.01") in JavaScript](#i-stumbled-upon-an-intriguing-string-to-number-conversion-technique-in-javascript)




## Did you know that you can optimize memory by changing the order of struct fields in Go?

<img src="https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExaHVmZ2hjeHg4em1vZjdnN284Zmt5cWs2YnUzYWk0M3d5dW16OW9jaCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/lXu72d4iKwqek/giphy.gif" alt="Mind Blown" style="width: 100">


Its fascinating! Right?

I didn't know this until I saw this for myself in a reddit thread's example. Now this is not a new thing. Programming languages like C/C++ already has this concepts up and running for decades.

Turns out, most processors access data more efficiently when data is aligned to certain byte boundaries (e.g., 2, 4, 8 bytes). For instance, an int64 (which is 8 bytes) is most efficiently accessed when stored at a memory address that is a multiple of 8. To achieve this alignment, Go automatically adds padding between fields in a struct. This padding can increase the size of a struct if fields are not ordered optimally.

By ordering fields from largest to smallest, you minimise the amount of padding required between fields, resulting in a smaller overall memory footprint.

Here are the links where I found this:-


The Example: https://go.dev/play/p/MBXg4UBOerp

The Thread: https://www.reddit.com/r/golang/comments/qcab7p/you_can_optimize_memory_by_changing_the_order_of/

Additional Read: https://www.wagslane.dev/posts/go-struct-ordering/


## I stumbled upon an intriguing string-to-number conversion technique in JavaScript

"1000.01"*1 is faster than Number("1000.01")

![Fast!!!!](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExcnU2NXl3dHdvMjFhYjN0dnd4Y3lzeGVsaW90ZzUwaGZ0N2V0bGMzMSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/3ornjYNHp6WwEdq3cc/giphy.gif)

The operation "1000.01"*1 involves using the multiplication operator with a numeric value (1), which implicitly converts the string to a number and is generally faster because it's a simple operation involving the multiplication operator. In contrast, Number("1000.01") requires calling a function (Number), which introduces some overhead.

Now, that doesn’t mean you're going to replace every line of string-to-number conversion code that uses the (Number) function with multiplication by 1. 
😅 

While it is fast, you might encounter some precision issues, so you should avoid using it in places where precision is critical.

There is a good Stack Overflow thread discussing various string-to-number conversion techniques in JavaScript and their benchmarks. Definitely check it out.

[Link to the Stack Overflow post](https://stackoverflow.com/questions/1133770/how-to-convert-a-string-to-an-integer-in-javascript)
