# custompost
Crete custom post for Wordpress
At first copy the below code and paste on functions.php file

// Register Custom Post Type
function meteor_custom_posts() {

	$labels = array(
		'name'                  => _x( 'Home Sliders', 'Post Type General Name', 'meteor' ),
		'singular_name'         => _x( 'Home Slider', 'Post Type Singular Name', 'meteor' ),
		'menu_name'             => __( 'Home Slider', 'meteor' ),
		'name_admin_bar'        => __( 'Home Slider', 'meteor' ),
		'archives'              => __( 'Slider Archives', 'meteor' ),
		'attributes'            => __( 'Slider Attributes', 'meteor' ),
		'parent_item_colon'     => __( 'Parent Item:', 'meteor' ),
		'all_items'             => __( 'All Sliders', 'meteor' ),
		'add_new_item'          => __( 'Add New Slider', 'meteor' ),
		'add_new'               => __( 'Add New Slide', 'meteor' ),
		'new_item'              => __( 'New Slide', 'meteor' ),
		'edit_item'             => __( 'Edit Slide', 'meteor' ),
		'update_item'           => __( 'Update Slider', 'meteor' ),
		'view_item'             => __( 'View Slider', 'meteor' ),
		'view_items'            => __( 'View Sliders', 'meteor' ),
		'search_items'          => __( 'Search Slider', 'meteor' ),
		'not_found'             => __( 'NO slider', 'meteor' ),
		'not_found_in_trash'    => __( 'Not found in Trash', 'meteor' ),
		'featured_image'        => __( 'Slider Featured Image', 'meteor' ),
		'set_featured_image'    => __( 'Set Slider image', 'meteor' ),
		'remove_featured_image' => __( 'Remove Slider image', 'meteor' ),
		'use_featured_image'    => __( 'Use as Slider image', 'meteor' ),
		'insert_into_item'      => __( 'Insert into Slide', 'meteor' ),
		'uploaded_to_this_item' => __( 'Uploaded to this slider', 'meteor' ),
		'items_list'            => __( 'Slider List', 'meteor' ),
		'items_list_navigation' => __( 'Slider list navigation', 'meteor' ),
		'filter_items_list'     => __( 'Filter Slider list', 'meteor' ),
	);
	$args = array(
		'label'                 => __( 'Home Slider', 'meteor' ),
		'description'           => __( 'This is Home page Slider', 'meteor' ),
		'labels'                => $labels,
		'supports'              => array( 'title', 'editor', 'thumbnail' ),
		'taxonomies'            => array( 'category', 'post_tag' ),
		'hierarchical'          => false,
		'public'                => true,
		'show_ui'               => true,
		'show_in_menu'          => true,
		'menu_position'         => 5,
		'menu_icon'             => 'dashicons-images-alt2',
		'show_in_admin_bar'     => true,
		'show_in_nav_menus'     => true,
		'can_export'            => true,
		'has_archive'           => true,
		'exclude_from_search'   => false,
		'publicly_queryable'    => true,
		'capability_type'       => 'page',
	);
	register_post_type( 'home_slider', $args );

}
add_action( 'init', 'meteor_custom_posts', 0 );




Step2: Make query post in slider teplate like

#newSlider=new WP_Query(array(

  'post_type' => __('home_slider', 'text-domain'),
  'posts_per_page' => 1

))
