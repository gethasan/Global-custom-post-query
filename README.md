Global-custom-post-query
========================

<?php
global $post;
$args = array( 'posts_per_page' => 10, 'post_type'=> 'custom-post-type' );
$myposts = get_posts( $args );
foreach( $myposts as $post ) : setup_postdata($post); ?>

    <?php 
        $job_link= get_post_meta($post->ID, 'job_instructions', true); 
    ?>

	<h2><?php the_title(); ?></h2>
	<?php the_content(); ?>
	<p><?php echo $job_link; ?></p>
<?php endforeach; ?>
