---
layout: post
title: PyTorch Toolkit
description: >
  Useful PyTorch code snippets
image: 
  path: /assets/img/blog/pt_blog.jpg
  srcset:
    1060w: /assets/img/blog/pt_blog.jpg
    530w:  /assets/img/blog/pt_blog_50.jpg
    265w:  /assets/img/blog/pt_blog_25.jpg
invert_sidebar: true
---

## PyTorch Toolkit

PyTorch is an open-source deep learning framework developed by Facebook's AI Research lab and has been widely
used for research and production in various machine learning tasks, including computer vision, natural language processing, and reinforcement learning.

* toc
{:toc .large-only}


## Tensor Fundamentals
In PyTorch, Tensors serve as a fundamental building block, enabling efficient numerical computations on various devices, such as CPUs, GPUs, and TPUs.

#### Create Tensor
~~~python
    print("Create a 1D tensor of size 10 with values from 1 to 10: ")
    X = torch.arange(1, 11, 1)
    print(X, "\n")

    print("Create a 2D tensor of size 3x3 with random values: ")
    X = torch.randn(3, 3)
    print(X, "\n")

    print("Create a tensor filled with zeros of shape (4, 5): ")
    X = torch.zeros(4, 5)
    print(X, "\n")

    print("Create a tensor filled with ones of shape (2, 6): ")
    X = torch.ones(2, 6)
    print(X, "\n")

    print("Create a tensor with the same shape as another tensor, filled with a specified value (e.g., 7): ")
    Y = torch.full_like(X, 7)
    print(Y, "\n")
~~~

#### Element-wise Addition, Subtraction, Multiplication, Division
~~~python
    print("Perform element-wise addition of two tensors: ")
    X = torch.ones(3, 4)
    Y = torch.ones(3, 4)
    result = X + Y
    print(result, "\n")

    print("Perform element-wise subtraction of two tensors: ")
    X = torch.ones(3, 4)
    Y = torch.ones(3, 4)
    result = X - Y
    print(result, "\n")

    print("Perform element-wise multiplication of two tensors: ")
    X = torch.ones(3, 4)
    Y = torch.ones(3, 4)
    result = X * Y
    print(result, "\n")

    print("Perform element-wise division of two tensors: ")
    X = torch.randn(3, 4)
    Y = torch.randn(3, 4)
    result = X / Y
    print(result, "\n")
~~~

#### Multiplication
~~~python
    print("Perform matrix multiplication of two 2D tensors \n")
    print("torch.mm: matrix multiplication without broadcasting, expects two 2D tensors so n x m * m x p = n x p")
    X = torch.randn(3, 4) # (B, T, C)
    Y = torch.ones(4, 3)
    result = torch.mm(X, Y)
    print(result, "\n")

    print("torch.mul: performs a elementwise multiplication with broadcasting, tensor by (tensor or number)")
    a = torch.FloatTensor([[1], [2], [3]])
    b = torch.FloatTensor([[1, 10, 100]])
    a, b = torch.broadcast_tensors(a, b)
    print(a)
    print(b)
    print(a * b) # element-wise multiplication
    print(torch.mul(a, b)) # 

    print("torch.matmul: matrix product with broadcasting")
    print("vector x vector")
    tensor1 = torch.randn(3)
    tensor2 = torch.randn(3)
    res = torch.matmul(tensor1, tensor2)
    print(res)
    print(f"tensor1 shape is {tensor1.shape}, tensor2 shape is {tensor2.shape}, res shape is {res.shape}\n")

    print("matrix x vector")
    tensor1 = torch.randn(3, 4)
    tensor2 = torch.randn(4)
    res = torch.matmul(tensor1, tensor2)
    print(f"tensor1 shape is {tensor1.shape}, tensor2 shape is {tensor2.shape}, res shape is {res.shape}\n")

    print("batched matrix times broadcasted vector")
    tensor1 = torch.randn(10, 3, 4)
    tensor2 = torch.randn(4)
    res = tensor1.matmul(tensor2)
    print(f"tensor1 shape is {tensor1.shape}, tensor2 shape is {tensor2.shape}, res shape is {res.shape}\n")

    print("batched matrix x batched matrix")
    tensor1 = torch.randn(10, 3, 4)
    tensor2 = torch.randn(10, 4, 5)
    res = tensor1.matmul(tensor2)
    print(f"tensor1 shape is {tensor1.shape}, tensor2 shape is {tensor2.shape}, res shape is {res.shape}\n")

    print("batched matrix x broadcasted matrix")
    tensor1 = torch.randn(10, 3, 4)
    tensor2 = torch.randn(1, 4, 5)
    res = tensor1.matmul(tensor2)
    print(f"tensor1 shape is {tensor1.shape}, tensor2 shape is {tensor2.shape}, res shape is {res}\n")
~~~

#### Dot Product
~~~python
    tensor1 = torch.ones(4)
    tensor2 = torch.ones(4)
    res = tensor1.dot(tensor2)
    print(f"tensor1 shape is {tensor1.shape}, tensor2 shape is {tensor2.shape}, res shape is {res}\n")
~~~

#### Mean, Standard Deviation, Variance, Summation
~~~python
    tensor1 = torch.randn(10, 3, 4)
    print(f"torch shape is {tensor1.shape}")
    print(f"res shape along dim 0 is {tensor1.mean(dim=0, keepdim=True).shape}")
    print(f"res shape along dim 1 is {tensor1.mean(dim=1, keepdim=True).shape}")
    print(f"res shape along dim 2 is {tensor1.mean(dim=2, keepdim=True).shape}")

    print(f"res shape along dim 0 is {tensor1.std(dim=0, keepdim=True).shape}")
    print(f"res shape along dim 1 is {tensor1.std(dim=1, keepdim=True).shape}")
    print(f"res shape along dim 2 is {tensor1.std(dim=2, keepdim=True).shape}")

    print(f"res shape along dim 0 is {tensor1.var(dim=0, keepdim=True).shape}")
    print(f"res shape along dim 1 is {tensor1.var(dim=1, keepdim=True).shape}")
    print(f"res shape along dim 2 is {tensor1.var(dim=2, keepdim=True).shape}")

    print(f"res shape along dim 0 is {tensor1.sum(dim=0, keepdim=True).shape}")
    print(f"res shape along dim 1 is {tensor1.sum(dim=1, keepdim=True).shape}")
    print(f"res shape along dim 2 is {tensor1.sum(dim=2, keepdim=True).shape}")
~~~

#### Max, Min
~~~python
    tensor1 = torch.randn(10, 3, 4)
    print(f"torch shape is {tensor1.shape}")
    res0, indices = tensor1.max(dim=0, keepdim=True)
    res1 = tensor1.max(dim=1, keepdim=True)
    res2 = tensor1.max(dim=2, keepdim=True)

    print(f"res shape along dim 0 is {res0.shape}")
    print(f"res shape along dim 1 is {res1[0].shape}")
    print(f"res shape along dim 2 is {res2[0].shape}")

    _, indices = tensor1.max(dim=0, keepdim=True)
    print(indices)
~~~

#### Indexing
~~~python
    print("Select a specific element from a 2D tensor")
    tensor_2d = torch.tensor([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
    element = tensor_2d[1, 2]
    print("Specific element:", element, "\n")

    print(tensor_2d)

    print("Select a row from a 2D tensor")
    row = tensor_2d[1, :]
    print(f"Selected row {row}\n")

    print("Select a column from a 2D tensor")
    col = tensor_2d[:, 1]
    print(f"Selected col {col}\n")

    print("Slice a tensor to get a sub-tensor")
    sub_tensor = tensor_2d[0:2, 1:3] # first 2 row, last 2 col
    print(f"Sub-tensor {sub_tensor}\n")
~~~

#### Concatenate, Stack
~~~python
    print("Concatenate two tensors along a specific dimension")
    tensor1 = torch.tensor([[1, 2], [3, 4]])
    tensor2 = torch.tensor([[5, 6], [7, 8]])
    concat_tensor = torch.cat((tensor1, tensor2), dim=0)
    print(f"Concatenated tensor along dim 0 {concat_tensor}")

    print("Stack two tensors along a new dimension")
    tensor1 = torch.randn(3, 3)
    tensor2 = torch.randn(3, 3)
    stacked_tensor = torch.stack((tensor1, tensor2), dim=0)
    print(f"Stacked tensor along new dimension dim 0 {stacked_tensor.shape}")
    print(f"tensor {stacked_tensor}")

    stacked_tensor = torch.stack((tensor1, tensor2), dim=1)
    print(f"Stacked tensor along new dimension dim 1 {stacked_tensor.shape}")
    print(f"tensor {stacked_tensor}")

    stacked_tensor = torch.stack((tensor1, tensor2), dim=2)
    print(f"Stacked tensor along new dimension dim 1 {stacked_tensor.shape}")
    print(f"tensor {stacked_tensor}")
~~~

#### Reshape
~~~python
    print("reshape from a vector")
    tensor = torch.arange(0, 27).reshape(3, 3, 3)
    print(f"reshape from a vector {tensor}")

    print("Reshape from a tensor from shape (4, 5) to (5, 4)")
    tensor = torch.arange(0, 20).reshape(4, 5)
    print(f"original tensor {tensor}, with shape {tensor.shape}")
    tensor_reshaped = tensor.reshape(5, 4)
    print(f"reshaped tensor {tensor_reshaped}, with shape {tensor_reshaped.shape}")

    print("reshape a 3D tensor")
    tensor = torch.arange(10 * 24).reshape(10, 24) # including 0
    print(f"3D tensor before reshaping the last dim {tensor.shape}")

    tensor_reshaped = tensor.reshape(10, 6, 4)
    print(f"3D tensor after reshaping the last dim {tensor_reshaped.shape}")

    tensor_reshaped_2 = tensor.reshape(10, 2, 3, 4)
    print(f"4D tensor after reshaping the last dim {tensor_reshaped_2.shape}")

    print("view")
    tensor = torch.arange(0, 8).reshape(2, 2, 2)
    print(f"before flatten {tensor}")
    print(f"after flatten {tensor.reshape(-1)}")

    tensor = torch.arange(0, 6).view(2, 3)
    print(f"1D to 2D tensor {tensor}")
~~~

#### Squeeze, Unsqueewze
~~~python
    print("Squeeze a tensor with single dimensions")
    tensor1 = torch.randn(1, 3, 1, 4)
    tensor_squeezed_1 = tensor1.squeeze(0)
    print(f"tensor_squeezed shape {tensor_squeezed_1.shape}")

    tensor_squeezed_2 = tensor1.squeeze()
    print(f"tensor_squeezed shape {tensor_squeezed_2.shape}")

    tensor2 = torch.randn(3, 4)
    tensor2_squeezed_1 = tensor2.unsqueeze(0).unsqueeze(2)
    print(f"tensor_squeezed shape {tensor2_squeezed_1.shape}")
~~~

#### Permute
~~~python
    tensor = torch.arange(0, 24).reshape(2, 3, 4)
    print(f"before permute {tensor}, with shape {tensor.shape}")
    tensor_permuted = tensor.permute(2, 1, 0)
    print(f"after permute {tensor_permuted}, with shape {tensor_permuted.shape}")
~~~

#### Select Top K
~~~python
    t = torch.tensor([
        [10, 20, 30, 40],
        [50, 60, 70, 80],
        [90, 100, 110, 120]
    ])
    topk_values, topk_indices = torch.topk(t, k=3, dim=1)
    print("Original Tensor:")
    print(t)
    print("\nTop 3 Values along dimension 1:")
    print(topk_values)
    print("\nIndices of Top 3 Values along dimension 1:")
    print(topk_indices)
~~~

## Code Block Headers
Code blocks can now have headers:

~~~js
// file: 'hello-world.js'
console.log('Hello World!');
~~~

Headers are added by making the first line a comment of the form `(file|title): ['"].*['"]`, e.g.:

    ~~~js
    // file: 'hello-world.js'
    console.log('Hello World!');
    ~~~
    
Code blocks with and without headers now also come with a copy button. 
In the case of header-less code blocks, the button only shows on hover to prevent potential overlap.


## Resume Download Buttons
Resumes can now have download buttons:

![Download Buttons](/assets/img/blog/9.1.0-3.png){:.border.lead width="1776" height="258" loading="lazy"}

Resumes can now have download buttons.
{:.figcaption}

The documentation has been updated with a chapter on [how to configure the buttons](/docs/basics/#downloads).


## SERP Breadcrumbs
Added breadcrumbs above page title:

![Breadcrumbs](/assets/img/blog/9.1.0-2.png){:.border.lead width="1588" height="164" loading="lazy"}

Bread crumbs are now shown above each page title.
{:.figcaption}

Note that this requires a [directory-like URL structure](https://qwtel.com/posts/software/urls-are-directories/) on your entire site, 
otherwise the intermediate links will point to nonexisting sites.

On a side note, Hydejack now has built-in tooltips for abbreviations like SERP (activated via tap/click).
See [Example Content](/blog/hyde/2012-02-07-example-content/#inline-html-elements) on how to add them to your content.


## Last Modified At
Blog posts can now have a "last modified at" date in the sub title row.

![Last modified at](/assets/img/blog/9.1.0-1.png){:.border.lead width="1254" height="218" loading="lazy"}

Note that this depends on the `last_modified_at` property of the page, which must be either set manually in the frontmatter (not recommended), or via a plugin like [`jekyll-last-modified-at`](https://github.com/gjtorikian/jekyll-last-modified-at). Note that the later is not available when building on GitHub Pages and can increase build times.


## Clap Button Preview
I've been trying something new with [**getclaps.app**](https://getclaps.app/), a feedback and analytics tool for personal sites like those powered by Hydejack. 

<!-- <clap-button style="--clap-button-color:var(--body-color);margin:2rem auto 3rem;width:3rem;height:3rem;font-size:smaller" nowave></clap-button> -->

It is a separate product from Hydejack and not enabled by default. Because it depends on a backend component, it requires a monthly fee. 
If enabled, it is placed below posts and pages where the dingbat character (❖) used to be.

I can't claim that this product is fully baked (feedback welcome), but I've been using it on my personal site and here for the last couple of months with no issues.
For more, see [the dedicated website](https://getclaps.app/).

***
{:style="margin:2rem 0"}

There are many more changes and bugfixes in 9.1. See the [CHANGELOG](/CHANGELOG/){:.heading.flip-title} for details.


## Credits

<span>Photo by <a href="https://unsplash.com/@jjying?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">JJ Ying</a> on <a href="https://unsplash.com/?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>

*[SERP]: Search Engine Results Page
