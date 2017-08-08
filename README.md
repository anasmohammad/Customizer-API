# Customizer-API

// Logo Settings

	$wp_customize->add_section( 'custom_logo', array(
			'title'    => __( 'Upload Logo', 'team' ),
			'priority' => 150, // Before Additional CSS.
		) );

		$wp_customize->add_setting( 'team_logo', array(
			'default'           => 'Test Name',
			'transport'         => 'postMessage',
			
		) );


		$wp_customize->add_control(
	       new WP_Customize_Image_Control(
	           $wp_customize,
	           'custom_logo',
	           array(
	               'label'      => __( 'Upload a logo', 'theme_name' ),
	               'section'    => 'custom_logo',
	               'settings'   => 'team_logo',
	               'context'    => 'your_setting_context' 
	           )
	       )
	   );


// ECHO OUT 

  <?php if( get_theme_mod( 'team_logo' ) != "" ): ?>
    <a href=""><img src="<?php echo get_theme_mod( 'team_logo' ); ?>" alt=""></a>
  <?php endif ?>
