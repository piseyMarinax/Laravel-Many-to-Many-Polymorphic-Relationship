# Laravel-Many-to-Many-Polymorphic-Relationship

+ Retrieve Records:

$post = Post::find(1);	
dd($post->tags);

$video = Video::find(1);	
dd($video->tags);

$tag = Tag::find(1);	 
dd($tag->posts);

$tag = Tag::find(1);	 
dd($tag->videos);

-----------------------------------------------

+ Create Records:

$post = Post::find(1);	
$tag = new Tag;
$tag->name = "ItSolutionStuff.com";
$post->tags()->save($tag);

$video = Video::find(1);	
$tag = new Tag;
$tag->name = "ItSolutionStuff.com";
$video->tags()->save($tag);

$post = Post::find(1);	
$tag1 = new Tag;
$tag1->name = "ItSolutionStuff.com";
$tag2 = new Tag;
$tag2->name = "ItSolutionStuff.com 2";
$post->tags()->saveMany([$tag1, $tag2]);

$video = Video::find(1);	
 
$tag1 = new Tag;
$tag1->name = "ItSolutionStuff.com";
$tag2 = new Tag;
$tag2->name = "ItSolutionStuff.com 2";
$video->tags()->saveMany([$tag1, $tag2]);

$post = Post::find(1);	
$tag1 = Tag::find(3);
$tag2 = Tag::find(4);
$post->tags()->attach([$tag1->id, $tag2->id]);

$video = Video::find(1);	
$tag1 = Tag::find(3);
$tag2 = Tag::find(4);
$video->tags()->attach([$tag1->id, $tag2->id]);

$post = Post::find(1);	
$tag1 = Tag::find(3);
$tag2 = Tag::find(4);
$post->tags()->sync([$tag1->id, $tag2->id]);

$video = Video::find(1);	
$tag1 = Tag::find(3);
$tag2 = Tag::find(4);
$video->tags()->sync([$tag1->id, $tag2->id]);
