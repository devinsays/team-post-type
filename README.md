## Team Post Type

This is meant to be used a custom post type boilerplate plugin- though it does work fine out of the box as a team post type.

### Description

This plugin includes a couple common features that are used with custom post types:

* Registers a post type
* Registers a custom taxonomy
* Registers a few metaboxes (Title, Twitter, Facebook, LinkedIn)
* Adds the featured image to the admin column display
* Adds the post count to the admin dashboard

### Customization

There are a couple filters for the post type and taxonomy arguments in this plugin, but the code is actually meant to be modified directly.

If you want to change this post type from "team" to something different ("products","resources",etc.) you'll want to update a couple file and class names throughout the plugin- but the main modifications will be in the "class-post-type-registrations.php" file.  This is where the post type and taxonomy are registered.

For information on all the available arguments, [read the codex for register_post_type](http://codex.wordpress.org/Function_Reference/register_post_type).

For example, if you were switching the post type from "team" to "products", you would want to alter this code.

#### Registration for "Team"

~~~PHP
$labels = array(
	'name'               => __( 'Team', 'team-post-type' ),
	'singular_name'      => __( 'Team Member', 'team-post-type' ),
	'add_new'            => __( 'Add Profile', 'team-post-type' ),
	'add_new_item'       => __( 'Add Profile', 'team-post-type' ),
	'edit_item'          => __( 'Edit Profile', 'team-post-type' ),
	'new_item'           => __( 'New Team Member', 'team-post-type' ),
	'view_item'          => __( 'View Profile', 'team-post-type' ),
	'search_items'       => __( 'Search Team', 'team-post-type' ),
	'not_found'          => __( 'No profiles found', 'team-post-type' ),
	'not_found_in_trash' => __( 'No profiles in the trash', 'team-post-type' ),
);

$supports = array(
	'title',
	'editor',
	'thumbnail',
	'custom-fields',
	'revisions',
);

$args = array(
	'labels'          => $labels,
	'supports'        => $supports,
	'public'          => true,
	'capability_type' => 'post',
	'rewrite'         => array( 'slug' => 'team', ), // Permalinks format
	'menu_position'   => 30,
	'menu_icon'       => 'dashicons-id',
);
~~~

#### Registration for "Product"

~~~PHP
$labels = array(
	'name'               => __( 'Products', 'team-post-type' ),
	'singular_name'      => __( 'Product', 'team-post-type' ),
	'add_new'            => __( 'Add Product', 'team-post-type' ),
	'add_new_item'       => __( 'Add Product', 'team-post-type' ),
	'edit_item'          => __( 'Edit Product', 'team-post-type' ),
	'new_item'           => __( 'New Product', 'team-post-type' ),
	'view_item'          => __( 'View Product', 'team-post-type' ),
	'search_items'       => __( 'Search Products', 'team-post-type' ),
	'not_found'          => __( 'No products found', 'team-post-type' ),
	'not_found_in_trash' => __( 'No products in the trash', 'team-post-type' ),
);

$supports = array(
	'title',
	'editor',
	'thumbnail',
	'custom-fields',
	'revisions',
);

$args = array(
	'labels'          => $labels,
	'supports'        => $supports,
	'public'          => true,
	'capability_type' => 'post',
	'rewrite'         => array( 'slug' => 'product', ), // Permalinks format
	'menu_position'   => 30,
	'menu_icon'       => 'dashicons-cart',
);
~~~

To find different icons to use ("menu_icon" parameter) see the [dashicons page](http://melchoyce.github.io/dashicons/).

### Requirements

* WordPress 3.8 or higher

### Frequently Asked Questions

#### Why did you make this?

To save myself time when custom post types are required for client projects.

#### Is this plugin on the WordPress repo?

No.  It's meant to be more of a white-label plugin to use for your own client projects.

### Credits

Built by [Devin Price](http://www.wptheming.com/).  The "Dashboard Glancer" class and much re-used code from the Portfolio Post Type plugin by [Gary Jones](http://gamajo.com/).