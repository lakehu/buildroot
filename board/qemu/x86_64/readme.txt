### weston test 
// guest kernel 5.15
#Host Ubuntu20/qemu7.2 

qemu-system-x86_64 -cpu host -m 1024m -kernel output/images/bzImage -drive file=output/images/rootfs.ext2,if=virtio,format=raw -append "console=ttyS0  root=/dev/vda" -net nic,model=virtio   -enable-kvm     -net user  -serial `tty`   -vga virtio   -display sdl,gl=es
Linux version 5.15.0 (uie75906@hid3915u) (x86_64-buildroot-linux-gnu-gcc.br_real (Buildroot 2021.11-3-g7317c56c87) 10.3.0, GNU ld (GNU Binutils) 2.36.1) #1 SMP Sat Sep 24 14:19:26 CST 2022
Command line: console=ttyS0  root=/dev/vda
............
[drm] pci: virtio-vga detected at 0000:00:02.0
virtio-pci 0000:00:02.0: vgaarb: deactivate vga console
Console: switching to colour dummy device 80x25
[drm] features: -virgl +edid -resource_blob -host_visible
[drm] number of scanouts: 1
[drm] number of cap sets: 0
[drm] Initialized virtio_gpu 0.1.0 0 for virtio0 on minor 0


Welcome to Buildroot
buildroot login: root
# mkdir /tmp/wayland  ;  chmod 0700 /tmp/wayland
# XDG_RUNTIME_DIR=/tmp/wayland  weston    --tty=1 
Date: 2022-09-24 UTC
[06:37:42.289] weston 9.0.0
               https://wayland.freedesktop.org
               Bug reports to: https://gitlab.freedesktop.org/wayland/weston/issues/
               Build: 2021.11-3-g7317c56c87
[06:37:42.310] Command line: weston --tty=1
[06:37:42.311] OS: Linux, 5.15.0, #1 SMP Sat Sep 24 14:19:26 CST 2022, x86_64
[06:37:42.312] Starting with no config file.
[06:37:42.313] Output repaint window is 7 ms maximum.
[06:37:42.314] Loading module '/usr/lib/libweston-9/drm-backend.so'
[06:37:42.316] initializing drm backend
[06:37:42.316] using /dev/dri/card0
[06:37:42.317] DRM: supports atomic modesetting
[06:37:42.317] DRM: does not support GBM modifiers
[06:37:42.318] DRM: supports picture aspect ratio
[06:37:42.319] Loading module '/usr/lib/libweston-9/gl-renderer.so'
urandom_read: 3 callbacks suppressed
random: weston: uninitialized urandom read (8 bytes read)
random: weston: uninitialized urandom read (8 bytes read)
random: weston: uninitialized urandom read (8 bytes read)
[06:37:42.349] EGL client extensions: EGL_EXT_client_extensions
               EGL_EXT_device_base EGL_EXT_device_enumeration
               EGL_EXT_device_query EGL_EXT_platform_base
               EGL_KHR_client_get_all_proc_addresses EGL_KHR_debug
               EGL_EXT_platform_device EGL_EXT_platform_wayland
               EGL_KHR_platform_wayland EGL_MESA_platform_gbm
               EGL_KHR_platform_gbm EGL_MESA_platform_surfaceless
[06:37:42.356] EGL version: 1.4
[06:37:42.357] EGL vendor: Mesa Project
[06:37:42.357] EGL client APIs: OpenGL OpenGL_ES 
[06:37:42.358] EGL extensions: EGL_ANDROID_blob_cache EGL_EXT_buffer_age
               EGL_EXT_image_dma_buf_import
               EGL_EXT_image_dma_buf_import_modifiers EGL_KHR_cl_event2
               EGL_KHR_config_attribs EGL_KHR_create_context
               EGL_KHR_create_context_no_error EGL_KHR_fence_sync
               EGL_KHR_get_all_proc_addresses EGL_KHR_gl_colorspace
               EGL_KHR_gl_renderbuffer_image EGL_KHR_gl_texture_2D_image
               EGL_KHR_gl_texture_3D_image EGL_KHR_gl_texture_cubemap_image
               EGL_KHR_image EGL_KHR_image_base EGL_KHR_image_pixmap
               EGL_KHR_no_config_context EGL_KHR_reusable_sync
               EGL_KHR_surfaceless_context EGL_EXT_pixel_format_float
               EGL_KHR_wait_sync EGL_MESA_configless_context
               EGL_MESA_image_dma_buf_export EGL_MESA_query_driver
[06:37:42.380] warning: Disabling render GPU timeline and explicit synchronization due to missing EGL_ANDROID_native_fence_sync extension
[06:37:42.382] EGL_KHR_surfaceless_context available
[06:37:42.419] GL version: OpenGL ES 3.1 Mesa 21.1.8
[06:37:42.420] GLSL version: OpenGL ES GLSL ES 3.10
[06:37:42.420] GL vendor: Mesa/X.org
[06:37:42.421] GL renderer: softpipe
[06:37:42.421] GL extensions: GL_EXT_blend_minmax GL_EXT_multi_draw_arrays
               GL_EXT_texture_filter_anisotropic
               GL_EXT_texture_compression_s3tc GL_EXT_texture_compression_dxt1
               GL_EXT_texture_compression_rgtc GL_EXT_texture_format_BGRA8888
               GL_OES_compressed_ETC1_RGB8_texture GL_OES_depth24
               GL_OES_element_index_uint GL_OES_fbo_render_mipmap
               GL_OES_mapbuffer GL_OES_rgb8_rgba8 GL_OES_standard_derivatives
               GL_OES_stencil8 GL_OES_texture_3D GL_OES_texture_float
               GL_OES_texture_float_linear GL_OES_texture_half_float
               GL_OES_texture_half_float_linear GL_OES_texture_npot
               GL_OES_vertex_half_float GL_EXT_draw_instanced
               GL_EXT_texture_sRGB_decode GL_OES_EGL_image
               GL_OES_depth_texture GL_OES_packed_depth_stencil
               GL_EXT_texture_type_2_10_10_10_REV GL_NV_conditional_render
               GL_OES_get_program_binary GL_APPLE_texture_max_level
               GL_EXT_discard_framebuffer GL_EXT_read_format_bgra
               GL_EXT_frag_depth GL_NV_fbo_color_attachments
               GL_OES_EGL_image_external GL_OES_EGL_sync
               GL_OES_vertex_array_object GL_OES_viewport_array
               GL_ANGLE_pack_reverse_row_order
               GL_ANGLE_texture_compression_dxt3
               GL_ANGLE_texture_compression_dxt5
               GL_EXT_occlusion_query_boolean GL_EXT_texture_rg
               GL_EXT_unpack_subimage GL_NV_draw_buffers GL_NV_read_buffer
               GL_NV_read_depth GL_NV_read_depth_stencil GL_NV_read_stencil
               GL_EXT_draw_buffers GL_EXT_map_buffer_range GL_KHR_debug
               GL_KHR_texture_compression_astc_ldr GL_NV_pixel_buffer_object
               GL_OES_depth_texture_cube_map GL_OES_required_internalformat
               GL_OES_surfaceless_context GL_EXT_color_buffer_float
               GL_EXT_sRGB_write_control GL_EXT_separate_shader_objects
               GL_EXT_shader_implicit_conversions GL_EXT_shader_integer_mix
               GL_EXT_base_instance GL_EXT_compressed_ETC1_RGB8_sub_texture
               GL_EXT_copy_image GL_EXT_draw_buffers_indexed
               GL_EXT_draw_elements_base_vertex GL_EXT_gpu_shader5
               GL_EXT_primitive_bounding_box GL_EXT_render_snorm
               GL_EXT_shader_io_blocks GL_EXT_texture_border_clamp
               GL_EXT_texture_buffer GL_EXT_texture_cube_map_array
               GL_EXT_texture_norm16 GL_EXT_texture_view
               GL_KHR_context_flush_control GL_NV_image_formats
               GL_OES_copy_image GL_OES_draw_buffers_indexed
               GL_OES_draw_elements_base_vertex GL_OES_gpu_shader5
               GL_OES_primitive_bounding_box GL_OES_shader_io_blocks
               GL_OES_texture_border_clamp GL_OES_texture_buffer
               GL_OES_texture_cube_map_array GL_OES_texture_stencil8
               GL_OES_texture_storage_multisample_2d_array GL_OES_texture_view
               GL_EXT_blend_func_extended GL_EXT_float_blend
               GL_EXT_geometry_point_size GL_EXT_geometry_shader
               GL_EXT_texture_sRGB_R8 GL_EXT_texture_sRGB_RG8 GL_KHR_no_error
               GL_KHR_texture_compression_astc_sliced_3d
               GL_OES_EGL_image_external_essl3 GL_OES_geometry_point_size
               GL_OES_geometry_shader GL_OES_shader_image_atomic
               GL_EXT_clip_cull_distance GL_EXT_disjoint_timer_query
               GL_EXT_texture_compression_s3tc_srgb
               GL_MESA_shader_integer_functions GL_EXT_clip_control
               GL_EXT_color_buffer_half_float GL_EXT_texture_compression_bptc
               GL_KHR_parallel_shader_compile GL_EXT_EGL_image_storage
               GL_MESA_framebuffer_flip_y GL_EXT_depth_clamp
               GL_EXT_texture_query_lod
[06:37:42.483] GL ES 2 renderer features:
               read-back format: BGRA
               wl_shm sub-image to texture: yes
               EGL Wayland extension: no
[06:37:42.492] event0  - Power Button: is tagged by udev as: Keyboard
[06:37:42.493] event0  - Power Button: device is a keyboard
[06:37:42.494] event1  - AT Translated Set 2 keyboard: is tagged by udev as: Keyboard
[06:37:42.495] event1  - AT Translated Set 2 keyboard: device is a keyboard
[06:37:42.497] event2  - ImExPS/2 Generic Explorer Mouse: is tagged by udev as: Mouse
[06:37:42.498] event2  - ImExPS/2 Generic Explorer Mouse: device is a pointer
[06:37:42.509] libinput: configuring device "Power Button".
[06:37:42.510] libinput: configuring device "AT Translated Set 2 keyboard".
[06:37:42.510] libinput: configuring device "ImExPS/2 Generic Explorer Mouse".
[06:37:42.511] DRM: head 'Virtual-1' found, connector 34 is connected, EDID make 'RHT', model 'QEMU Monitor', serial 'unknown'
[06:37:42.513] Registered plugin API 'weston_drm_output_api_v1' of size 24
[06:37:42.513] Chosen EGL config details: id:  16 rgba: 8 8 8 0 buf: 24 dep:  0 stcl: 0 int: 1-1 type: win vis_id: XRGB8888 (0x34325258)
[06:37:42.515] Output Virtual-1 (crtc 33) video modes:
               1280x800@75.0, preferred, current, 107.3 MHz
               5120x2160@50.0 64:27, 742.5 MHz
               4096x2160@50.0 256:135, 594.0 MHz
               3840x2160@60.0 16:9, 594.0 MHz
               3840x2160@59.9 16:9, 593.4 MHz
               3840x2160@50.0 16:9, 594.0 MHz
               1920x1440@60.0, 234.0 MHz
               2560x1080@50.0 64:27, 185.6 MHz
               1856x1392@60.0, 218.2 MHz
               1792x1344@60.0, 204.8 MHz
               2048x1152@60.0, 162.0 MHz
               1920x1200@59.9, 193.2 MHz
               1920x1080@60.0, 148.5 MHz
               1920x1080@50.0 16:9, 148.5 MHz
               1600x1200@60.0, 162.0 MHz
               1680x1050@60.0, 146.2 MHz
               1400x1050@60.0, 121.8 MHz
               1280x1024@60.0, 108.0 MHz
               1440x900@59.9, 106.5 MHz
               1280x960@60.0, 108.0 MHz
               1360x768@60.0, 85.5 MHz
               1280x768@59.9, 79.5 MHz
               1024x768@60.0, 65.0 MHz
               800x600@60.3, 40.0 MHz
               640x480@60.0 4:3, 25.2 MHz
               640x480@59.9, 25.2 MHz
[06:37:42.527] associating input device event0 with output Virtual-1 (none by udev)
[06:37:42.528] associating input device event1 with output Virtual-1 (none by udev)
[06:37:42.529] associating input device event2 with output Virtual-1 (none by udev)
[06:37:42.530] Output 'Virtual-1' enabled with head(s) Virtual-1
[06:37:42.530] Compositor capabilities:
               arbitrary surface rotation: yes
               screen capture uses y-flip: yes
               presentation clock: CLOCK_MONOTONIC, id 1
               presentation clock resolution: 0.004000000 s
[06:37:42.534] Loading module '/usr/lib/weston/desktop-shell.so'
[06:37:42.535] launching '/usr/libexec/weston-keyboard'
[06:37:42.536] weston_client_launch: fork failed while launching '/usr/libexec/weston-keyboard': Cannot allocate memory
[06:37:42.540] not able to start /usr/libexec/weston-keyboard
[06:37:42.541] launching '/usr/libexec/weston-desktop-shell'
[06:37:42.542] weston_client_launch: fork failed while launching '/usr/libexec/weston-desktop-shell': Cannot allocate memory
[06:37:42.543] not able to start /usr/libexec/weston-desktop-shell
virtio_gpu virtio0: [drm] drm_plane_enable_fb_damage_clips() not called
^Z[1]+  Stopped                    weston --tty=1
# bg
[1] weston --tty=1
# XDG_RUNTIME_DIR=/tmp/wayland   weston-terminal
could not load cursor 'dnd-move'
could not load cursor 'dnd-copy'
could not load cursor 'dnd-none'
xkbcommon: ERROR: couldn't find a Compose file for locale "C" (mapped to "C")
could not create XKB compose table for locale 'C'.  Disabiling compose



#####  
kmscube with Mesa3d/GALLIUM driver to test DRM/EGL
# kmscube
urandom_read: 3 callbacks suppressed
random: kmscube: uninitialized urandom read (8 bytes read)
random: kmscube: uninitialized urandom read (8 bytes read)
random: kmscube: uninitialized urandom read (8 bytes read)
Using display 0x5a4a80 with EGL version 1.4
===================================
EGL information:
  version: "1.4"
  vendor: "Mesa Project"
  client extensions: "EGL_EXT_client_extensions EGL_EXT_device_base EGL_EXT_device_enumeration EGL_EXT_device_query EGL_EXT_platform_base EGL_KHR_client_get_all_proc_addresses EGL_KHR_debug EGL_EXT_platform_device EGL_EXT_platform_wayland EGL_KHR_platform_wayland EGL_MESA_platform_gbm EGL_KHR_platform_gbm EGL_MESA_platform_surfaceless"
  display extensions: "EGL_ANDROID_blob_cache EGL_EXT_buffer_age EGL_EXT_image_dma_buf_import EGL_EXT_image_dma_buf_import_modifiers EGL_KHR_cl_event2 EGL_KHR_config_attribs EGL_KHR_create_context EGL_KHR_create_context_no_error EGL_KHR_fence_sync EGL_KHR_get_all_proc_addresses EGL_KHR_gl_colorspace EGL_KHR_gl_renderbuffer_image EGL_KHR_gl_texture_2D_image EGL_KHR_gl_texture_3D_image EGL_KHR_gl_texture_cubemap_image EGL_KHR_image EGL_KHR_image_base EGL_KHR_image_pixmap EGL_KHR_no_config_context EGL_KHR_reusable_sync EGL_KHR_surfaceless_context EGL_EXT_pixel_format_float EGL_KHR_wait_sync EGL_MESA_configless_context EGL_MESA_image_dma_buf_export EGL_MESA_query_driver "
===================================
OpenGL ES 2.x information:
  version: "OpenGL ES 3.1 Mesa 20.3.4"
  shading language version: "OpenGL ES GLSL ES 3.10"
  vendor: "Mesa/X.org"
  renderer: "softpipe"
  extensions: "GL_EXT_blend_minmax GL_EXT_multi_draw_arrays GL_EXT_texture_filter_anisotropic GL_EXT_texture_compression_s3tc GL_EXT_texture_compression_dxt1 GL_EXT_texture_compression_rgtc GL_EXT_texture_format_BGRA8888 GL_OES_compressed_ETC1_RGB8_texture GL_OES_depth24 GL_OES_element_index_uint GL_OES_fbo_render_mipmap GL_OES_mapbuffer GL_OES_rgb8_rgba8 GL_OES_standard_derivatives GL_OES_stencil8 GL_OES_texture_3D GL_OES_texture_float GL_OES_texture_float_linear GL_OES_texture_half_float GL_OES_texture_half_float_linear GL_OES_texture_npot GL_OES_vertex_half_float GL_EXT_draw_instanced GL_EXT_texture_sRGB_decode GL_OES_EGL_image GL_OES_depth_texture GL_OES_packed_depth_stencil GL_EXT_texture_type_2_10_10_10_REV GL_NV_conditional_render GL_OES_get_program_binary GL_APPLE_texture_max_level GL_EXT_discard_framebuffer GL_EXT_read_format_bgra GL_EXT_frag_depth GL_NV_fbo_color_attachments GL_OES_EGL_image_external GL_OES_EGL_sync GL_OES_vertex_array_object GL_OES_viewport_array GL_ANGLE_pack_reverse_row_order GL_ANGLE_texture_compression_dxt3 GL_ANGLE_texture_compression_dxt5 GL_EXT_occlusion_query_boolean GL_EXT_texture_rg GL_EXT_unpack_subimage GL_NV_draw_buffers GL_NV_read_buffer GL_NV_read_depth GL_NV_read_depth_stencil GL_NV_read_stencil GL_EXT_draw_buffers GL_EXT_map_buffer_range GL_KHR_debug GL_KHR_texture_compression_astc_ldr GL_NV_pixel_buffer_object GL_OES_depth_texture_cube_map GL_OES_required_internalformat GL_OES_surfaceless_context GL_EXT_color_buffer_float GL_EXT_sRGB_write_control GL_EXT_separate_shader_objects GL_EXT_shader_implicit_conversions GL_EXT_shader_integer_mix GL_EXT_base_instance GL_EXT_compressed_ETC1_RGB8_sub_texture GL_EXT_copy_image GL_EXT_draw_buffers_indexed GL_EXT_draw_elements_base_vertex GL_EXT_gpu_shader5 GL_EXT_primitive_bounding_box GL_EXT_render_snorm GL_EXT_shader_io_blocks GL_EXT_texture_border_clamp GL_EXT_texture_buffer GL_EXT_texture_cube_map_array GL_EXT_texture_norm16 GL_EXT_texture_view GL_KHR_context_flush_control GL_NV_image_formats GL_OES_copy_image GL_OES_draw_buffers_indexed GL_OES_draw_elements_base_vertex GL_OES_gpu_shader5 GL_OES_primitive_bounding_box GL_OES_shader_io_blocks GL_OES_texture_border_clamp GL_OES_texture_buffer GL_OES_texture_cube_map_array GL_OES_texture_stencil8 GL_OES_texture_storage_multisample_2d_array GL_OES_texture_view GL_EXT_blend_func_extended GL_EXT_float_blend GL_EXT_geometry_point_size GL_EXT_geometry_shader GL_KHR_no_error GL_KHR_texture_compression_astc_sliced_3d GL_OES_EGL_image_external_essl3 GL_OES_geometry_point_size GL_OES_geometry_shader GL_OES_shader_image_atomic GL_EXT_clip_cull_distance GL_EXT_disjoint_timer_query GL_EXT_texture_compression_s3tc_srgb GL_MESA_shader_integer_functions GL_EXT_clip_control GL_EXT_color_buffer_half_float GL_EXT_texture_compression_bptc GL_KHR_parallel_shader_compile GL_EXT_EGL_image_storage GL_EXT_texture_sRGB_R8 GL_MESA_framebuffer_flip_y GL_EXT_depth_clamp GL_EXT_texture_query_lod "

Run the emulation with:

  qemu-system-x86_64 -cpu host -kernel output/images/bzImage -drive file=output/images/rootfs.ext2,if=virtio,format=raw -append "rootwait root=/dev/vda console=tty1 console=ttyS0" -serial stdio -net nic,model=virtio -net user -enable-kvm -vga virtio -display sdl,gl=es # qemu_x86_64_defconfig

 

Optionally add -smp N to emulate a SMP system with N CPUs.

The login prompt will appear in the graphical window.
