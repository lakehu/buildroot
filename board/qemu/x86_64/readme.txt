Run the emulation with:

  qemu-system-x86_64 -cpu host -m 1024m -kernel output/images/bzImage -drive file=output/images/rootfs.ext2,if=virtio,format=raw -append "rootwait root=/dev/vda console=tty1 console=ttyS0" -serial stdio -net nic,model=virtio -net user -enable-kvm -vga virtio -display sdl,gl=es # qemu_x86_64_defconfig

Optionally add -smp N to emulate a SMP system with N CPUs.

The login prompt will appear in the graphical window.


Note: kms/drm/openGLes on X86 with qemu-x86 

# DRM/virtio_gpu is OK from modetest, OpenGL ES//kmscube can't get more fps(30fps)  
#exec qemu-system-x86_64 -cpu host -m 1024m -kernel bzImage -drive file=rootfs.ext2,if=virtio,format=raw -append "rootwait root=/dev/vda console=tty1 console=ttyS0"  -net nic,model=virtio -net user -enable-kvm -device virtio-gpu-pci -display sdl   -serial stdio

# DRM/virtio_gpu is OK from modetest, OpenGL ES both are supported,kmscube/opengl/kms can't get more fps (30fps) ****
#exec qemu-system-x86_64 -cpu host -m 1024m -kernel bzImage -drive file=rootfs.ext2,if=virtio,format=raw -append "rootwait root=/dev/vda console=tty1 console=ttyS0"  -net nic,model=virtio -net user -enable-kvm -vga virtio -display sdl,gl=es   -serial stdio

# bochs VGA/no DRM, OpenGL ES//kmscube can get more fps >60fps
#exec qemu-system-x86_64 -cpu host -m 1024m -kernel bzImage -drive file=rootfs.ext2,if=virtio,format=raw -append "rootwait root=/dev/vda console=tty1 console=ttyS0"  -net nic,model=virtio -net user -enable-kvm -vga std -display sdl,gl=es   -serial stdio


# bochs VGA/no DRM, OpenGL ES//kmscube can get more fps >60fps
#exec qemu-system-x86_64 -cpu host  -m 1024m  -kernel bzImage -drive file=rootfs.ext2,if=virtio,format=raw -append "rootwait root=/dev/vda console=tty1 console=ttyS0"  -net nic,model=virtio -net user -enable-kvm -display sdl,gl=es  -serial stdio

Log when execute option2/ DRM/virtio_gpu is OK from modetest, OpenGL ES both are supported:  -enable-kvm -vga virtio -display sdl,gl=es 

Linux version 6.10.8 (uie75906@hid3915u) (x86_64-buildroot-linux-gnu-gcc.br_real (Buildroot 2024.08) 13.3.0, GNU ld (GNU Binutils) 2.41) #1 SMP PREEMPT_DYNAMIC Mon Dec  2 17:27:30 CST 2024
Command line: rootwait root=/dev/vda console=tty1 console=ttyS0

# ffmpeg  -hwaccels
ffmpeg version 6.1.2 Copyright (c) 2000-2024 the FFmpeg developers
  built with gcc 13.3.0 (Buildroot 2024.08)
  configuration: --enable-cross-compile --cross-prefix=/DATA2/uie75906/lfs/buildroot/output/host/bin/x86_64-buildroot-linux-gnu- --sysroot=/DATA2/uie75906/lfs/buildroot/output/host/x86_64-buildroot-linux-gnu/sysroot --host-cc=/usr/bin/gcc --arch=x86_64 --target-os=linux --disable-stripping --pkg-config=/DATA2/uie75906/lfs/buildroot/output/host/bin/pkg-config --disable-static --enable-shared --prefix=/usr --enable-avfilter --disable-version3 --enable-logging --enable-optimizations --disable-extra-warnings --enable-avdevice --enable-avcodec --enable-avformat --enable-network --disable-gray --enable-swscale-alpha --disable-small --disable-crystalhd --disable-dxva2 --enable-runtime-cpudetect --disable-hardcoded-tables --disable-mipsdsp --disable-mipsdspr2 --disable-msa --enable-hwaccels --disable-cuda --disable-cuvid --disable-nvenc --disable-avisynth --disable-frei0r --disable-libopencore-amrnb --disable-libopencore-amrwb --disable-libdc1394 --disable-libgsm --disable-libilbc --disable-libvo-amrwbenc --disable-symver --disable-doc --disable-gpl --disable-nonfree --enable-ffmpeg --enable-ffplay --disable-libjack --disable-libv4l2 --disable-ffprobe --disable-libxcb --disable-postproc --enable-swscale --enable-indevs --disable-alsa --enable-outdevs --enable-pthreads --enable-zlib --disable-bzlib --disable-libfdk-aac --disable-libcdio --disable-gnutls --disable-openssl --enable-libdrm --disable-libopenh264 --disable-vaapi --disable-vdpau --disable-mmal --disable-omx --disable-omx-rpi --disable-libopencv --disable-libopus --disable-libvpx --disable-libass --disable-libbluray --disable-libvpl --disable-libmfx --disable-librtmp --disable-libmp3lame --disable-libmodplug --disable-libspeex --disable-libtheora --disable-iconv --disable-libfreetype --disable-fontconfig --disable-libopenjpeg --disable-libx264 --disable-libx265 --disable-libdav1d --enable-x86asm --enable-sse --enable-sse2 --disable-sse3 --disable-ssse3 --disable-sse4 --disable-sse42 --disable-avx --disable-avx2 --disable-armv6 --disable-armv6t2 --disable-vfp --disable-neon --disable-altivec --extra-libs=-latomic --enable-pic --cpu=x86-64
  libavutil      58. 29.100 / 58. 29.100
  libavcodec     60. 31.102 / 60. 31.102
  libavformat    60. 16.100 / 60. 16.100
  libavdevice    60.  3.100 / 60.  3.100
  libavfilter     9. 12.100 /  9. 12.100
  libswscale      7.  5.100 /  7.  5.100
  libswresample   4. 12.100 /  4. 12.100
Hardware acceleration methods:
drm


# modetest 
trying to open device 'i915'...failed
trying to open device 'amdgpu'...failed
trying to open device 'radeon'...failed
trying to open device 'nouveau'...failed
trying to open device 'vmwgfx'...failed
trying to open device 'omapdrm'...failed
trying to open device 'exynos'...failed
trying to open device 'tilcdc'...failed
trying to open device 'msm'...failed
trying to open device 'sti'...failed
trying to open device 'tegra'...failed
trying to open device 'imx-drm'...failed
trying to open device 'rockchip'...failed
trying to open device 'atmel-hlcdc'...failed
trying to open device 'fsl-dcu-drm'...failed
trying to open device 'vc4'...failed
trying to open device 'virtio_gpu'...done
Encoders:
id	crtc	type	possible crtcs	possible clones	
38	0	Virtual	0x00000001	0x00000001

Connectors:
id	encoder	status		name		size (mm)	modes	encoders
37	0	connected	Virtual-1      	320x200		26	38
  modes:
	index name refresh (Hz) hdisp hss hse htot vdisp vss vse vtot
  #0 1280x800 74.99 1280 1600 1638 1728 800 804 808 828 107300 flags: nhsync, nvsync; type: preferred, driver
  #1 5120x2160 50.00 5120 6216 6304 6600 2160 2168 2178 2250 742500 flags: phsync, pvsync; type: driver
  #2 4096x2160 50.00 4096 5064 5152 5280 2160 2168 2178 2250 594000 flags: phsync, pvsync; type: driver
  #3 3840x2160 60.00 3840 4016 4104 4400 2160 2168 2178 2250 594000 flags: phsync, pvsync; type: driver
  #4 3840x2160 59.94 3840 4016 4104 4400 2160 2168 2178 2250 593407 flags: phsync, pvsync; type: driver
  #5 3840x2160 50.00 3840 4896 4984 5280 2160 2168 2178 2250 594000 flags: phsync, pvsync; type: driver
  #6 1920x1440 60.00 1920 2048 2256 2600 1440 1441 1444 1500 234000 flags: nhsync, pvsync; type: driver
  #7 2560x1080 50.00 2560 3108 3152 3300 1080 1084 1089 1125 185625 flags: phsync, pvsync; type: driver
  #8 1856x1392 60.00 1856 1952 2176 2528 1392 1393 1396 1439 218250 flags: nhsync, pvsync; type: driver
  #9 1792x1344 60.00 1792 1920 2120 2448 1344 1345 1348 1394 204750 flags: nhsync, pvsync; type: driver
  #10 2048x1152 60.00 2048 2074 2154 2250 1152 1153 1156 1200 162000 flags: phsync, pvsync; type: driver
  #11 1920x1200 59.88 1920 2056 2256 2592 1200 1203 1209 1245 193250 flags: nhsync, pvsync; type: driver
  #12 1920x1080 60.00 1920 2008 2052 2200 1080 1084 1089 1125 148500 flags: nhsync, nvsync; type: driver
  #13 1920x1080 50.00 1920 2448 2492 2640 1080 1084 1089 1125 148500 flags: phsync, pvsync; type: driver
  #14 1600x1200 60.00 1600 1664 1856 2160 1200 1201 1204 1250 162000 flags: phsync, pvsync; type: driver
  #15 1680x1050 59.95 1680 1784 1960 2240 1050 1053 1059 1089 146250 flags: nhsync, pvsync; type: driver
  #16 1400x1050 59.98 1400 1488 1632 1864 1050 1053 1057 1089 121750 flags: nhsync, pvsync; type: driver
  #17 1280x1024 60.02 1280 1328 1440 1688 1024 1025 1028 1066 108000 flags: phsync, pvsync; type: driver
  #18 1440x900 59.89 1440 1520 1672 1904 900 903 909 934 106500 flags: nhsync, pvsync; type: driver
  #19 1280x960 60.00 1280 1376 1488 1800 960 961 964 1000 108000 flags: phsync, pvsync; type: driver
  #20 1360x768 60.02 1360 1424 1536 1792 768 771 777 795 85500 flags: phsync, pvsync; type: driver
  #21 1280x768 59.87 1280 1344 1472 1664 768 771 778 798 79500 flags: nhsync, pvsync; type: driver
  #22 1024x768 60.00 1024 1048 1184 1344 768 771 777 806 65000 flags: nhsync, nvsync; type: driver
  #23 800x600 60.32 800 840 968 1056 600 601 605 628 40000 flags: phsync, pvsync; type: driver
  #24 640x480 60.00 640 656 752 800 480 490 492 525 25200 flags: nhsync, nvsync; type: driver
  #25 640x480 59.94 640 656 752 800 480 490 492 525 25175 flags: nhsync, nvsync; type: driver
  props:
	2 DPMS:
		flags: enum
		enums: On=0 Standby=1 Suspend=2 Off=3
		value: 0
	5 link-status:
		flags: enum
		enums: Good=0 Bad=1
		value: 0
	6 non-desktop:
		flags: immutable range
		values: 0 1
		value: 0
	4 TILE:
		flags: immutable blob
		blobs:

		value:
	1 EDID:
		flags: immutable blob
		blobs:

		value:
			00ffffffffffff004914341200000000
			2a180104a520147806ee91a3544c9926
			0f5054210800e1c0d1c0d100a940b300
			950081808140ea2900c051201c304026
			444045cb10000018000000f7000a0040
			82002820000000000000000000fd0032
			7d1ea0ff010a202020202020000000fc
			0051454d55204d6f6e69746f720a013a
			02030b00467d6560591f610000001000
			00000000000000000000000000000000
			10000000000000000000000000000000
			00001000000000000000000000000000
			00000000100000000000000000000000
			00000000000010000000000000000000
			00000000000000001000000000000000
			0000000000000000000000000000002f

CRTCs:
id	fb	pos	size
36	0	(0,0)	(0x0)
  #0  -nan 0 0 0 0 0 0 0 0 0 flags: ; type: 
  props:
	24 VRR_ENABLED:
		flags: range
		values: 0 1
		value: 0

Planes:
id	crtc	fb	CRTC x,y	x,y	gamma size	possible crtcs
32	0	0	0,0		0,0	0       	0x00000001
  formats: XR24
  props:
	8 type:
		flags: immutable enum
		enums: Overlay=0 Primary=1 Cursor=2
		value: 1
33	0	0	0,0		0,0	0       	0x00000001
  formats: AR24
  props:
	8 type:
		flags: immutable enum
		enums: Overlay=0 Primary=1 Cursor=2
		value: 2
	34 HOTSPOT_X:
		flags: signed range
		values: -2147483648 2147483647
		value: 0
	35 HOTSPOT_Y:
		flags: signed range
		values: -2147483648 2147483647
		value: 0

Frame buffers:
id	size	pitch



###########

PLANE(ID=32, W=1280, H=800)
      |
    \ | /
CRCT(ID=36) --> ENCODER(ID=38) --> CONNECTED(ID=37) --> virtio_gpu
###########

# modetest -M   virtio_gpu   -a -s 37@36:1280x800  -P 32@36:1280x800 -Ftiles  
setting mode 1280x800-74.99Hz on connectors 37, crtc 36
testing 1280x800@XR24 on plane 32, crtc 36



# kmscube 
Using display 0x5580aba5a0b0 with EGL version 1.4
===================================
EGL information:
  version: "1.4"
  vendor: "Mesa Project"
  client extensions: "EGL_EXT_client_extensions EGL_EXT_device_base EGL_EXT_device_enumeration EGL_EXT_device_query EGL_EXT_platform_base EGL_KHR_client_get_all_proc_addresses EGL_KHR_debug EGL_EXT_platform_device EGL_EXT_explicit_device EGL_MESA_platform_gbm EGL_KHR_platform_gbm EGL_MESA_platform_surfaceless"
  display extensions: "EGL_ANDROID_blob_cache EGL_EXT_buffer_age EGL_EXT_image_dma_buf_import EGL_EXT_image_dma_buf_import_modifiers EGL_KHR_cl_event2 EGL_KHR_config_attribs EGL_KHR_context_flush_control EGL_KHR_create_context EGL_KHR_create_context_no_error EGL_KHR_fence_sync EGL_KHR_get_all_proc_addresses EGL_KHR_gl_colorspace EGL_KHR_gl_renderbuffer_image EGL_KHR_gl_texture_2D_image EGL_KHR_gl_texture_3D_image EGL_KHR_gl_texture_cubemap_image EGL_KHR_image EGL_KHR_image_base EGL_KHR_image_pixmap EGL_KHR_no_config_context EGL_KHR_reusable_sync EGL_KHR_surfaceless_context EGL_EXT_pixel_format_float EGL_KHR_wait_sync EGL_MESA_configless_context EGL_MESA_gl_interop EGL_MESA_image_dma_buf_export EGL_MESA_query_driver "
===================================
OpenGL ES 2.x information:
  version: "OpenGL ES 3.1 Mesa 24.0.9"
  shading language version: "OpenGL ES GLSL ES 3.10"
  vendor: "Mesa"
  renderer: "softpipe"
  extensions: "GL_EXT_blend_minmax GL_EXT_multi_draw_arrays GL_EXT_texture_filter_anisotropic GL_EXT_texture_compression_s3tc GL_EXT_texture_compression_dxt1 GL_EXT_texture_compression_rgtc GL_EXT_texture_format_BGRA8888 GL_OES_compressed_ETC1_RGB8_texture GL_OES_depth24 GL_OES_element_index_uint GL_OES_fbo_render_mipmap GL_OES_mapbuffer GL_OES_rgb8_rgba8 GL_OES_standard_derivatives GL_OES_stencil8 GL_OES_texture_3D GL_OES_texture_float GL_OES_texture_float_linear GL_OES_texture_half_float GL_OES_texture_half_float_linear GL_OES_texture_npot GL_OES_vertex_half_float GL_EXT_draw_instanced GL_EXT_texture_sRGB_decode GL_OES_EGL_image GL_OES_depth_texture GL_OES_packed_depth_stencil GL_EXT_texture_type_2_10_10_10_REV GL_NV_conditional_render GL_OES_get_program_binary GL_APPLE_texture_max_level GL_EXT_discard_framebuffer GL_EXT_read_format_bgra GL_NV_pack_subimage GL_EXT_frag_depth GL_NV_fbo_color_attachments GL_OES_EGL_image_external GL_OES_EGL_sync GL_OES_vertex_array_object GL_OES_viewport_array GL_ANGLE_pack_reverse_row_order GL_ANGLE_texture_compression_dxt3 GL_ANGLE_texture_compression_dxt5 GL_EXT_occlusion_query_boolean GL_EXT_texture_rg GL_EXT_unpack_subimage GL_NV_draw_buffers GL_NV_read_buffer GL_NV_read_depth GL_NV_read_depth_stencil GL_NV_read_stencil GL_APPLE_sync GL_EXT_draw_buffers GL_EXT_instanced_arrays GL_EXT_map_buffer_range GL_KHR_debug GL_KHR_texture_compression_astc_ldr GL_NV_generate_mipmap_sRGB GL_NV_pixel_buffer_object GL_OES_depth_texture_cube_map GL_OES_required_internalformat GL_OES_surfaceless_context GL_EXT_color_buffer_float GL_EXT_debug_label GL_EXT_sRGB_write_control GL_EXT_separate_shader_objects GL_EXT_shader_implicit_conversions GL_EXT_shader_integer_mix GL_EXT_base_instance GL_EXT_compressed_ETC1_RGB8_sub_texture GL_EXT_copy_image GL_EXT_draw_buffers_indexed GL_EXT_draw_elements_base_vertex GL_EXT_gpu_shader5 GL_EXT_primitive_bounding_box GL_EXT_render_snorm GL_EXT_shader_io_blocks GL_EXT_texture_border_clamp GL_EXT_texture_buffer GL_EXT_texture_cube_map_array GL_EXT_texture_norm16 GL_EXT_texture_view GL_KHR_context_flush_control GL_NV_image_formats GL_NV_shader_noperspective_interpolation GL_OES_copy_image GL_OES_draw_buffers_indexed GL_OES_draw_elements_base_vertex GL_OES_gpu_shader5 GL_OES_primitive_bounding_box GL_OES_shader_io_blocks GL_OES_texture_border_clamp GL_OES_texture_buffer GL_OES_texture_cube_map_array GL_OES_texture_stencil8 GL_OES_texture_storage_multisample_2d_array GL_OES_texture_view GL_EXT_blend_func_extended GL_EXT_buffer_storage GL_EXT_float_blend GL_EXT_geometry_point_size GL_EXT_geometry_shader GL_EXT_texture_sRGB_R8 GL_EXT_texture_sRGB_RG8 GL_KHR_no_error GL_KHR_texture_compression_astc_sliced_3d GL_OES_EGL_image_external_essl3 GL_OES_geometry_point_size GL_OES_geometry_shader GL_OES_shader_image_atomic GL_EXT_clear_texture GL_EXT_clip_cull_distance GL_EXT_disjoint_timer_query GL_EXT_texture_compression_s3tc_srgb GL_MESA_shader_integer_functions GL_EXT_clip_control GL_EXT_color_buffer_half_float GL_EXT_texture_compression_bptc GL_EXT_texture_mirror_clamp_to_edge GL_KHR_parallel_shader_compile GL_EXT_EGL_image_storage GL_MESA_framebuffer_flip_y GL_EXT_depth_clamp GL_EXT_texture_query_lod GL_MESA_sampler_objects GL_MESA_bgra "
===================================
Rendered 48 frames in 2.032178 sec (23.619976 fps)
Rendered 126 frames in 4.051801 sec (31.097282 fps)
Rendered 186 frames in 6.076728 sec (30.608580 fps)

