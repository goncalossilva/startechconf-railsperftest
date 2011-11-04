!SLIDE
!SLIDE

# Simple pitfalls

!SLIDE

## Eager loading

!SLIDE

### 1 + N queries

    @@@ ruby
    has_many :comments
<br/>
    @@@ ruby
    belongs_to :post
<br/>
    @@@ ruby
    @posts = Post.all
<br/>
    @@@ ruby
    @posts.each do |post|
      post.comments.each do |comment|
        # ... ouch!
      end
    end

!SLIDE

### 2 queries

    @@@ ruby
    has_many :comments
<br/>
    @@@ ruby
    belongs_to :post
<br/>
    @@@ ruby
    @posts = Post.include(:comments).all
<br/>
    @@@ ruby
    @posts.each do |post|
      post.comments.each do |comment|
        # ... we're fine!
      end
    end

!SLIDE

## Transactions

!SLIDE

### One for every insert/update/delete

!SLIDE

### N transactions

    @@@ ruby
    (0..N).each do |n|
      Post.create(content: "This is post number #{n})
    end

!SLIDE

### 1 transaction

    @@@ ruby
    Post.transaction do
      (0..N).each do |n|
        Post.create(content: "This is post number #{n})
      end
    end

!SLIDE

## Loading too many objects at once

!SLIDE

## Upload/Download = Apache/Nginx

!SLIDE

## And many more!
