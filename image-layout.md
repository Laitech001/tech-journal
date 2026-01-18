# Fixing Product Image Layout Issues

Fixing Image alignment issue on product page
The problem: My product image are not align well on product page and they are scattering, some images are stable while some that have much padding and space in them are controlling the layout.

How I solve the problem
Solving the problem is not easy but I am able to solve it and it makes me happy and feel myself. 
Here is the Logic behind the problem: Don’t allow the image to control the container, let the container control the image.
Here is the solution: To make all images fit in a container, I wrapped my <img> element in a container like <div>, I gave the container a width and height, I make it flexible container and centre it child. Then I go to the <img> element (the main concern), I gave it a max-width of 100% and same thing to height too, and object-fit: container; so it can container the container

Achievement
At the end after all the stress and thinking for more than 2 weeks even after I ignore it and leave it like that, I still later go back to it and I make it work. This make me happy so much, what I did is small but if I give up and leave it like that, it won’t change itself and I won’t understand how it work

When it look very hard, don’t give up, keep moving

## Code
# Html
<div class="image-container">
  <img src="iphone-12.png" alt="iphone 12">
</div>

# css

.image-container {
  width: 300px;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.image-container img {
  max-width: 100%;
  max-height: 100%;
  object-fit: container;
}

# in general approach
keep your code clean, if something feels eavy and disturbing the page or controlling layout, I will try and remember this approach and use it to solve the problem, it will work in many ways
