<div class="github-widget" data-repo="vinjn/awesome-vulkan"></div>
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><ins class="adsbygoogle" style="display:block" data-ad-client="ca-pub-6890694312814945" data-ad-slot="5473692530" data-ad-format="auto"  data-full-width-responsive="true"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
## Awesome Vulkan [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

<img src="https://raw.githubusercontent.com/SaschaWillems/Vulkan/master/images/vulkanlogoscene.png" alt="Vulkan demo scene" height="256px">

精选的Vulkan库，调试器和资源的精选列表. 受启发 [awesome-opengl](https://github.com/eug/awesome-opengl) 和其他很棒的东西.

* **[Hardware Support](#hardware-support)**
* **[SDK](#sdk)**
* **[IHV Document](#document)**
* **[Tutorial](#tutorial)**
* **[Apps](#apps)**
* **[Samples](#samples)**
* **[Libraries](#libraries)**
* **[Bindings](#bindings)**
* **[Tools](#tools)**
* **[Books](#books)**
* **[Khronos](#khronos)**
* **[Community](#community)**

## Hardware Support
*  [gpuinfo](http://vulkan.gpuinfo.org/) -Sascha Willems的火山硬件数据库
*  [Khronos](https://www.khronos.org/vulkan)
*  [NVIDIA](https://developer.nvidia.com/Vulkan)
    *  [Driver for Desktop](https://developer.nvidia.com/vulkan-driver)
    *  [Driver for Android](https://developer.nvidia.com/vulkan-android)
    *  [Driver for Linux for Tegra (L4T)](https://developer.nvidia.com/embedded/vulkan)
*  [AMD](http://www.amd.com/en-gb/innovations/software-technologies/technologies-gaming/vulkan)
    *  [Open-source Driver](https://github.com/GPUOpen-Drivers/AMDVLK)
*  [Imagination](https://www.imgtec.com/developers/powervr-sdk-tools/)
*英特尔
    *  [Open-source Driver](https://01.org/linuxgraphics/blogs/jekstrand/2016/open-source-vulkan-drivers-intel-hardware/)
    *  [Driver for Windows](https://software.intel.com/en-us/blogs/2016/03/14/new-intel-vulkan-beta-1540204404-graphics-driver-for-windows-78110-1540)
*  [Qualcomm](https://developer.qualcomm.com/software/adreno-gpu-sdk/gpu)
*手臂
    *  [Mali GPU Best Practices](https://developer.arm.com/solutions/graphics/developer-guides/mali-gpu-best-practices)

## SDK
*  [For Windows & Linux](https://vulkan.lunarg.com/signin)
*  [For Android](https://developer.android.com/ndk/guides/graphics/index.html)

## Document
*  [AMD](http://gpuopen.com/tag/vulkan/)
    *  [Vulkan barriers explained](http://gpuopen.com/vulkan-barriers-explained/)
    *  [Vulkan Fast Paths](http://32ipi028l5q82yhj72224m8j.wpengine.netdna-cdn.com/wp-content/uploads/2016/03/VulkanFastPaths.pdf)
    *  [Let Your Game Shine – Optimizing DirectX 12 and Vulkan Performance with AMD CodeXL	](http://32ipi028l5q82yhj72224m8j.wpengine.netdna-cdn.com/wp-content/uploads/2016/03/Let_your_game_shine_optimizing_DirectX-12_and_Vulkan-performance_with_AMD_CodeXL.pdf)
    *  [D3D12 & Vulkan: Lessons Learned	 ](http://32ipi028l5q82yhj72224m8j.wpengine.netdna-cdn.com/wp-content/uploads/2016/03/d3d12_vulkan_lessons_learned.pdf)
    *  [Say Hello to a New Rendering API in Town!](http://gpuopen.com/say-hello/)
    *  [Vulkan Renderpasses](http://gpuopen.com/vulkan-renderpasses/)
    *  [Performance tweets series: Barriers, fences, synchronization](http://gpuopen.com/performance-tweets-series-barriers-fences-synchronization/)
    *  [Using the Vulkan™ Validation Layers](http://gpuopen.com/using-the-vulkan-validation-layers/)
    *  [Most common mistakes in Vulkan apps](http://32ipi028l5q82yhj72224m8j.wpengine.netdna-cdn.com/wp-content/uploads/2016/05/Most-common-mistakes-in-Vulkan-apps.pdf)
	*  [Vulkan Device Memory](http://gpuopen.com/vulkan-device-memory/)
*  [NVIDIA](https://developer.nvidia.com/taxonomy/term/586)
    * [Vulkan Device-Generated Commands](https://developer.nvidia.com/device-generated-commands-vulkan)
    * [Getting Vulkan Ready For VR](https://developer.nvidia.com/getting-vulkan-ready-vr)
    * [GPU-Driven Rendering](http://on-demand.gputechconf.com/gtc/2016/presentation/s6138-christoph-kubisch-pierre-boudier-gpu-driven-rendering.pdf)
    * [GDC 16 - High-performance, Low-Overhead Rendering with OpenGL and Vulkan](http://developer.download.nvidia.com/gameworks/events/GDC2016/mschott_lbishop_gl_vulkan.pdf)
    * [GDC 16 - Vulkan and NVIDIA – The Essentials](http://developer.download.nvidia.com/gameworks/events/GDC2016/Vulkan_Essentials_GDC16_tlorach.pdf)
    * [Engaging the Voyage to Vulkan](https://developer.nvidia.com/engaging-voyage-vulkan)
    * [Vulkan Shader Resource Binding](https://developer.nvidia.com/vulkan-shader-resource-binding)
    * [Vulkan Memory Management](https://developer.nvidia.com/vulkan-memory-management)
    * [OpenGL like Vulkan](https://developer.nvidia.com/opengl-vulkan)
    * [Transitioning from OpenGL to Vulkan](https://developer.nvidia.com/transitioning-opengl-vulkan)
    * [Siggraph 15 talk - Vulkan on NVIDIA GPUs](http://on-demand.gputechconf.com/siggraph/2015/presentation/SIG1501-Piers-Daniell.pdf)
*  [Arm](https://developer.arm.com/solutions/graphics/apis/vulkan)
    * [Vulkan Best Practice for Mobile Developers Tutorials](https://github.com/ARM-software/vulkan_best_practice_for_mobile_developers)
    * [Vulkan's Key Features on Arm Architecture](https://developer.arm.com/-/media/Files/pdf/graphics-and-multimedia/Vulkan%20API%20key%20features%20on%20ARM%20architecture.pdf)
    * [Porting a Graphics Engine to the Vulkan API](https://community.arm.com/groups/arm-mali-graphics/blog/2016/02/16/porting-a-graphics-engine-to-the-vulkan-api)
    * [Get Your Engine Ready for Vulkan on Mobile](https://developer.arm.com/-/media/Files/pdf/graphics-and-multimedia/Get%20Your%20Engine%20Ready%20for%20Vulkan%20on%20Mobile.pdf)
    * [Multi-Threading in Vulkan](https://community.arm.com/groups/arm-mali-graphics/blog/2016/04/19/massively-multi-thread-for-vulkan)
    * [Mali Vulkan SDK Tutorials](https://developer.arm.com/products/software/mali-sdks/vulkan) 和 [Slides](https://developer.arm.com/graphics/vulkan/vulkan-tutorials)
*英特尔
    * [API without Secrets: Introduction to Vulkan](https://github.com/GameTechDev/IntroductionToVulkan) [[LICENSE](https://github.com/GameTechDev/IntroductionToVulkan/blob/master/license.txt)]
        * [Part 1: The Beginning](https://software.intel.com/en-us/api-without-secrets-introduction-to-vulkan-part-1)
        * [Part 2: Swap Chain](https://software.intel.com/en-us/api-without-secrets-introduction-to-vulkan-part-2)
        * [Part 3: First Triangle](https://software.intel.com/en-us/api-without-secrets-introduction-to-vulkan-part-3)
        * [Part 4: Vertex Attributes](https://software.intel.com/en-us/articles/api-without-secrets-introduction-to-vulkan-part-4)
* [Imagination](http://blog.imgtec.com/tag/vulkan)
    * [Efficient Rendering with Vulkan on PowerVR](https://imagination-technologies-cloudfront-assets.s3.amazonaws.com/idc-docs/gdc16/6_Efficient%20rendering%20with%20Vulkan%20on%20PowerVR.pdf)
    * [Migrating to Vulkan with the New PowerVR Graphics Framework](https://www.imgtec.com/webinar/migrating-to-vulkan-with-the-powervr-framework/)
    * [Migrating from OpenGLES to Vulkan](https://www.imgtec.com/downloads/download-info/migrating-from-opengl-es-to-vulkan/)
* 三星
    * [Siggraph 2016 - Best Practices for Mobile](https://community.arm.com/cfs-file/__key/telligent-evolution-extensions-calendar-calendarfiles/00-00-00-00-05/2_2D00_mmg_2D00_siggraph2016_2D00_best_2D00_practice_2D00_andrew.pdf)
    * [Vulkan Usage Recommencation](https://developer.samsung.com/game/usage) （对于手机）
*史诗
    * [Efficient use of Vulkan on UE4 Mobile](https://community.arm.com/cfs-file/__key/telligent-evolution-extensions-calendar-calendarfiles/00-00-00-00-05/6_2D00_mmg_2D00_siggraph2016_2D00_vulkan_2D00_smedis.pdf)
* Khronos
   * [Vulkan Guide](https://github.com/KhronosGroup/Vulkan-Guide)
* [LunarG](https://lunarg.com)
    * [Vulkan SDK](https://vulkan.lunarg.com/)
    * [Vulkan SDK Version Compatibility](https://www.lunarg.com/wp-content/uploads/2020/03/Vulkan-SDK-Version-Compatibility_4_20.pdf)
    * [Introducing the New Vulkan Configurator](https://www.lunarg.com/wp-content/uploads/2020/08/Intro-to-Vulkan-Configurator_08_2020.pdf)
    * [Unified Validation Layer for Vulkan](https://www.lunarg.com/wp-content/uploads/2020/05/UberLayer_V3.pdf)
    * [Vulkan Synchronization Validation Quick Start Guide](https://www.lunarg.com/wp-content/uploads/2020/08/Final_Vulkan-Synchronization-Validation-Quick-Start_08_20.pdf)
    * [Guide to Vulkan Synchronization Validation](https://www.lunarg.com/wp-content/uploads/2020/09/Final_LunarG_Guide_to_Vulkan-Synchronization_Validation_08_20.pdf)
    * [Vulkan GPU-Assisted Validation](https://www.lunarg.com/wp-content/uploads/2020/05/GPU-Assisted-Validation-Phase-3_09_19.pdf)
    * [Automatic RelaxedPrecision Decoration and Conversion in Spirv-Opt](https://www.lunarg.com/wp-content/uploads/2020/05/Automatic-RelaxedPrecision-Decoration-and-Conversion-in-Spirv-Opt_r1.pdf)
    * [SPIR-V Legalization and Size Reduction with spirv-opt](https://www.lunarg.com/wp-content/uploads/2020/05/SPIR-V-Shader-Legalization-and-Size-Reduction-Using-spirv-opt_v1.2.pdf)
    * [All White Papers](https://www.lunarg.com/vulkan-white-papers/)

## Tutorial
*  [How to Learn Vulkan](https://www.jeremyong.com/c++/vulkan/graphics/rendering/2018/03/26/how-to-learn-vulkan.html) -关于如何学习Vulkan的元文章
*  [I Am Graphics And So Can You](https://www.fasterthan.life/blog/2017/7/11/i-am-graphics-and-so-can-you-part-1) -针对图形学习Vulkan的新手的博客文章样式教程.
*  [Moving to Vulkan (Khronos UK May16)](https://www.khronos.org/assets/uploads/developers/library/2016-uk-chapter-moving-to-vulkan/Moving-to-Vulkan_Khronos-UK_May16.pdf)
*  [jhenriques's tutorial](http://jhenriques.net/development.html)
*  [Lunarg's tutorial](https://vulkan.lunarg.com/doc/sdk/1.0.26.0/windows/tutorial.html)
*  [Mike Bailey's Vulkan Page](http://web.engr.oregonstate.edu/~mjb/vulkan/)  -提供丰富的Vulkan课程幻灯片.  [CC BY-NC-ND 4.0]
*  [Qualcomm Video Tutorial Series](https://developer.qualcomm.com/software/adreno-gpu-sdk/tutorial-videos) -向移动设备的Vulkan倾斜更多.
*  [Raw Vulkan](https://alain.xyz/blog/raw-vulkan) -有关如何从头开始编写Vulkan应用程序的概述.
* Siggraph
    * [An overview of next-generation graphics APIs](http://nextgenapis.realtimerendering.com/) -涵盖Vulkan，D3D12等
*  [Tutorial by Overv](https://vulkan-tutorial.com/) 和 [its github repository](https://github.com/Overv/VulkanTutorial) .  [CC BY-SA 4.0]
*  [vulkan-sxs](https://github.com/philiptaylor/vulkan-sxs) -逐步说明Vulkan API，并 [vulkan-sync](https://github.com/philiptaylor/vulkan-sync)  -以更精确的形式重新说明Vulkan对执行依赖项的要求.  [麻省理工学院]
*  [Vulkan in 30 minutes](https://renderdoc.org/vulkan-in-30-minutes.html) -by baldurk.
*  [Vulkan Demos and Tutorials](https://github.com/Z80Fan/VulkanDemos) .  [与]
*  [Vulkan Guide](https://vkguide.dev) .  [与]

## Apps
*  [The Talos Principle](http://www.croteam.com/talos-principle-will-support-vulkan-first-screenshot-released/) -由Croteam撰写.
*  [Dota2](https://github.com/ValveSoftware/Dota-2-Vulkan/) -通过阀门.
*  [Basemark](https://www.basemark.com/blog/basemark-extends-its-benchmarking-lead-with-a-vulkan-performance-test/) -通过Basemark.
*  [GFXBench 5](https://kishonti.net/news_single.jsp?id=31133884) -Kishonti.
*  [ProtoStar](https://www.unrealengine.com/blog/epic-games-unveils-protostar-at-samsung-galaxy-unpacked) -由Epic使用虚幻引擎4技术构建.
*  [Doom](https://en.wikipedia.org/wiki/Doom_(2016_video_game)）-通过id软件.
*  [vkQuake](https://github.com/Novum/vkQuake)  -基于QuakeSpasm的Vulkan Quake端口.  [GPL]
*  [vkQuake2](https://github.com/kondrak/vkQuake2)  -id Software的Quake 2 v3.21，具有Vulkan支持（Windows和Linux）.  [GPL]
*  [q2vkpt](https://github.com/cschied/q2vkpt/)  -实时路径跟踪器VKPT集成到q2pro Quake 2客户端中.  [gpl]
*  [Linux port of SteamVR](https://github.com/ValveSoftware/SteamVR-for-Linux) -SteamVR建立在Vulkan API之上.
*  [3DMark](https://www.futuremark.com/pressreleases/compare-vulkan-and-directx-12-performance-with-3dmark) - 3DMark API Overhead test.
*  [Q2RTX](https://github.com/NVIDIA/Q2RTX) -NVIDIA在Quake II中实现了RTX射线跟踪. [[LICENSE](https://github.com/NVIDIA/Q2RTX/blob/master/license.txt)]

## Samples
* Khronos [Vulkan samples](https://github.com/KhronosGroup/Vulkan-Samples) [[LICENSE](https://github.com/KhronosGroup/Vulkan-Samples/blob/master/LICENSE)]
*萨莎·威廉姆斯（Sascha Willems） [samples](https://github.com/SaschaWillems/Vulkan) 和 [Deferred rendering of Sponza](https://github.com/SaschaWillems/VulkanSponza) 和 his talk of [Khronos_meetup_munich](https://www.saschawillems.de/blog/2016/04/11/khronos-chapter-munich-vulkan-slides/).
*（不完整）Sascha Willems [samples port](https://github.com/jvm-graphics-labs/Vulkan) 去科特林
*萨莎·威廉姆斯（Sascha Willems） [Vulkan-glTF-PBR](https://github.com/SaschaWillems/Vulkan-glTF-PBR)  -使用glTF 2.0模型的Vulkan基于物理的渲染.  [麻省理工学院]
*  [Vulkan Best Practice for Mobile Developers Samples](https://github.com/ARM-software/vulkan_best_practice_for_mobile_developers)
* 谷歌
    *  [Android port of LunarG samples](https://github.com/googlesamples/vulkan-basic-samples).
    *  [android tutorials](https://github.com/googlesamples/android-vulkan-tutorials).
*  [nvpro-samples](https://github.com/nvpro-samples) -NVIDIA DesignWorks示例. [[LICENSE](https://github.com/nvpro-samples/gl_vk_threaded_cadscene/blob/master/LICENSE)]
    *  [gl_vk_chopper](https://github.com/nvpro-samples/gl_vk_chopper) -简单的vulkan渲染示例.
    *  [gl_vk_threaded_cadscene](https://github.com/nvpro-samples/gl_vk_threaded_cadscene) -OpenGL和Vulkan在使用各种技术渲染CAD场景时的比较 [the blog](https://developer.nvidia.com/vulkan-opengl-threaded-cad-scene-sample) 关于它.
    *  [gl_vk_bk3dthreaded](https://github.com/nvpro-samples/gl_vk_bk3dthreaded) -使用“工作线程”的Vulkan样本渲染3D.
    *  [gl_vk_supersampled](https://github.com/nvpro-samples/gl_vk_supersampled) -Vulkan样本显示了高质量的超级采样渲染.
*  [NVIDIA GameWorks Samples](https://github.com/NVIDIAGameWorks/GraphicsSamples) -GameWorks跨平台图形API示例. [[LICENSE](https://github.com/NVIDIAGameWorks/GraphicsSamples/blob/master/license.txt)]
*  [LunarG's Samples](https://github.com/LunarG/VulkanSamples)
*  [vkcube](https://github.com/krh/vkcube) -krh的“ vkcube”示例，可在X，Wayland和VT控制台下使用
drm/kms.
*  [Stardust from Intel](https://github.com/GameTechDev/stardust_vulkan) -Stardust示例应用程序使用Vulkan图形API有效地渲染了动画粒子云. [[LICENSE](https://github.com/GameTechDev/stardust_vulkan/blob/master/license.txt)]
*  [Vulkan Quake port based on QuakeSpasm](https://github.com/Novum/vkQuake).
*  [C# Samples](https://github.com/FacticiusVir/SharpVk-Samples) -Overv的教程移植到 [SharpVk](https://github.com/FacticiusVir/SharpVk) [与]
*  [Vulkan-Forward-Plus-Renderer](https://github.com/WindyDarian/Vulkan-Forward-Plus-Renderer)  -VFPR-Vulkan Forward Plus渲染器.  [与]
*  [Laugh Engine](https://github.com/jian-ru/laugh_engine) -实时PBR渲染器的Vulkan实现.
*  [tinyrenderers](https://github.com/chaoticbob/tinyrenderers) -Vulkan和D3D12渲染器的单头实现.
*  [TLVulkanRenderer](https://github.com/trungtle/TLVulkanRenderer)  -有关实时透明度的硕士论文的基于Vulkan的简单渲染器.  [CC BY-SA 4.0]
*  [Vulkan-Hpp Samples](https://github.com/jherico/Vulkan) -Sascha Willems的叉子使用Vulkan-Hpp制作的出色Vulkan示例.
*  [SDF Font Demo](https://github.com/kocsis1david/font-demo)  -通过估计符号距离在Vulkan中进行文本渲染.  [麻省理工学院]
*  [vulkantoy](https://github.com/jpystynen/vulkantoy)  -使用Vulkan的Shadertoy图像着色器测试应用程序.  [与]
*  [GL_vs_VK](https://github.com/RippeR37/GL_vs_VK)  -在性能方面比较OpenGL和Vulkan API.  [麻省理工学院]
*  [Vulkan Basic Graphics Samples](https://github.com/vcoda/basic-graphics-samples) -收集使用Magma库编写的简单图形样本.
*  [Simple RTX Vulkan raytracing tutorials](https://github.com/iOrange/rtxON) .  [与]
*  [RadX](https://github.com/world8th/RadX) -在GPU上进行基数排序的专用示例（特别是在NVIDIA RTX上）.
*  [Ray Tracing In One Weekend (Vulkan RTX)](https://github.com/GPSnoopy/RayTracingInVulkan) -使用Vulkan和NVIDIA的RTX扩展实现Peter Shirley的《光线追踪在一个周末》一书.
*  [Gears VK](https://github.com/jeffboody/gearsvk)  -Gears VK是著名的“齿轮”演示程序到Vulkan / Android / Linux的重大修改端口.  [麻省理工学院]
*  [Hello Triangle](https://github.com/helixd-2k18/VK_KHR_ray_tracing) ，基于`VK_KHR_ray_tracing`扩展名.  [麻省理工学院]

## Libraries
*  [Acid](https://github.com/Equilibrium-Games/Acid)  -高速C ++ 17 Vulkan游戏引擎.  [麻省理工学院]
*  [bgfx](https://github.com/bkaradzic/bgfx#bgfx---cross-platform-rendering-library) -与跨平台，图形API无关的“自带引擎/框架”样式渲染库. [[BSD-2-clause](https://github.com/bkaradzic/bgfx/blob/master/LICENSE)]
*  [bsf](https://github.com/GameFoundry/bsf)  -用于实时图形应用程序开发的现代C ++ 14库.  [麻省理工学院]
*  [Cinder](https://github.com/cinder/Cinder) 和 [the story](https://libcinder.org/notes/vulkan) [behind](https://forum.libcinder.org/#Topic/23286000002614007) .  [BSD]
*  [Diligent Engine](https://github.com/DiligentGraphics/DiligentEngine)  -支持OpenGL / GLES，Direct3D11 / 12和Vulkan的现代跨平台底层图形库.  [Apache许可2.0]
*  [SDL](https://discourse.libsdl.org/t/sdl-2-0-6-released/23109)  -在SDL_vulkan.h中添加了跨平台Vulkan图形支持.  [zlib]
*  [DemoFramework](https://github.com/NXPmicro/gtec-demo-framework) -NXP GTEC C ++ 11跨平台演示框架，包括用于Vulkan，OpenGL ES，OpenVX，OpenCL，OpenVG和OpenCV的许多示例. [[BSD-3-clause](https://github.com/NXPmicro/gtec-demo-framework/blob/master/License.md)]
*  [openFrameworks](https://github.com/openframeworks-vk/openFrameworks)  -最著名的C ++创新编码框架.  [麻省理工学院]
*  [PowerVR SDK](https://github.com/powervr-graphics/Native_SDK) -C ++跨平台3D图形SDK，可加快Vulkan和GLES的开发. [[LICENSE](https://github.com/powervr-graphics/Native_SDK/blob/4.1/LICENSE_POWERVR_SDK.txt)]
*  [glfw](https://github.com/glfw/glfw) 和 [the guide](http://www.glfw.org/docs/3.2/vulkan.html).  [[LICENSE](https://github.com/glfw/glfw/blob/master/LICENSE.md)]
*  [MoltenVK](https://github.com/KhronosGroup/MoltenVK/)  -在iOS和macOS上运行Vulkan.  [Apache-2.0]
*  [imgui](https://github.com/ocornut/imgui)  -立即模式图形用户界面.  [麻省理工学院]
*  [vuh](https://github.com/Glavnokoman/vuh)  -基于Vulkan的C ++ GPGPU计算框架.  [麻省理工学院]
*  [vk-bootstrap](https://github.com/charles-lunarg/vk-bootstrap)  -C ++实用程序库，可通过自动执行实例，物理设备，设备和交换链创建来快速启动Vulkan开发.  [麻省理工学院]
*  [liblava](https://github.com/liblava/liblava)  -一个现代的C ++和易于使用的框架.  [麻省理工学院]
*  [libvc](https://github.com/alexhultman/libvc) -适用于C ++的Vulkan Compute.  [[LICENSE](https://github.com/alexhultman/libvc/blob/master/LICENSE)]
*  [AMD's Anvil](https://github.com/GPUOpen-LibrariesAndSDKs/Anvil) -Vulkan的跨平台框架. [[LICENSE](https://github.com/GPUOpen-LibrariesAndSDKs/Anvil/blob/master/LICENSE.txt)]
    * [Introductory Vulkan sample](https://github.com/GPUOpen-LibrariesAndSDKs/HelloVulkan) .  [与]
*  [Vulkan Memory Allocator](https://github.com/GPUOpen-LibrariesAndSDKs/VulkanMemoryAllocator)  -易于集成AMD的Vulkan内存分配库.  [麻省理工学院]
*  [V-EZ](https://github.com/GPUOpen-LibrariesAndSDKs/V-EZ)  -面向专业工作站ISV的Vulkan API的轻量级中间件层.  [麻省理工学院]
*  [Google's vulkan-cpp-library](https://github.com/google/vulkan-cpp-library)  -使用C ++ 11的Vulkan抽象库，用于内存，资源管理，类型和线程安全以及系统独立性.  [Apache]
*  [Vookoo](https://github.com/andy-thomason/Vookoo)  -Vookoo是一组无依赖实用程序，可帮助构建和更新Vulkan图形数据结构.  [麻省理工学院]
*  [vpp](https://github.com/nyorain/vpp)  -现代C ++ Vulkan抽象关注于性能和简单的界面.  [麻省理工学院]
*  [Intrinsic Engine](https://github.com/begla/Intrinsic)  -Intrinsic是基于Vulkan的跨平台图形和游戏引擎.  [Apache许可2.0]
*  [glo / OpenGL Overload](https://github.com/g-truc/glo) -在Vulkan之上的OpenGL实现.
*  [Skia](https://skia.googlesource.com/skia) -Google的2D图形库有一个 [Vulkan](https://skia.org/user/special/vulkan) [backend](https://github.com/google/skia/tree/master/src/gpu/vk)，以跨平台演示 [sample application](https://skia.org/user/sample/viewer) 有自己 [window library](https://github.com/google/skia/tree/master/tools/viewer). [BSD 3-clause] [website](https://skia.org)
*  [Spectrum](https://github.com/mwalczyk/spectrum_core) -围绕Vulkan的在制品框架和抽象层.
*  [VkHLF](https://github.com/nvpro-pipeline/VkHLF)  -Vulkan高级框架.  [[许可证]]（https://github.com/nvpro-pipeline/VkHLF/blob/master/LICENSE.txt）
*  [VulkanOnD3D12](https://github.com/Chabloom/VulkanOnD3D12)  -D3D12的Vulkan API.  [Apache许可2.0]
*  [visor](https://github.com/baldurk/visor)  -Vulkan可忽略软件光栅器.  [与]
*  [Lugdunum](https://github.com/Lugdunum3D/Lugdunum)  -使用Vulkan和现代C ++ 14构建的现代跨平台3D渲染引擎.  [麻省理工学院]
*  [Vulkan-WSIWindow](https://github.com/renelindsay/Vulkan-WSIWindow)  -多平台库，用于创建Vulkan窗口并处理输入事件.  [Apache许可2.0]
*  [Falcor](https://github.com/NVIDIAGameWorks/Falcor)  -来自NVIDIA的实时渲染框架，支持DX12和Vulkan.  [BSD 3句]
*  [The-Forge](https://github.com/ConfettiFX/The-Forge)  -DirectX 12，Vulkan，macOS Metal 2渲染框架.  [Apache许可2.0]
*  [FrameGraph](https://github.com/azhirnov/FrameGraph)  -将框架表示为任务图的Vulkan抽象层.  [BSD 2句]
*  [VK9](https://github.com/disks86/VK9) -使用Vulkan的Direct3D 9兼容性层
*  [gfx-rs](https://github.com/gfx-rs/gfx)  -用于Rust的高性能，无绑定图形API.  [Apache许可2.0]
*  [vRt](https://github.com/world8th/vRt)  -基于Vulkan API（&gt; = 1.1）的统一光线跟踪库.  [LGPL-3.0]
*  [rostkatze](https://github.com/msiglreith/rostkatze) -位于D3D12上的Vulkan的C ++实现[Apache License 2.0]
*  [Fossilize](https://github.com/Themaister/Fossilize)  -各种持久性Vulkan对象类型的序列化格式.  [麻省理工学院]
*  [VulkanSceneGraph](https://github.com/vsg-dev) -Vulkan / C ++ 17场景图项目，后继项目 [OpenSceneGraph](http://www.openscenegraph.org).
*  [clspv](https://github.com/google/clspv)  -用于OpenCL C到Vulkan计算着色器的子集的原型编译器.  [Apache许可2.0]
*  [Pumex](https://github.com/pumexx/pumex)  -实现框架图和简单场景图的跨平台Vulkan渲染器. 能够一次在多个表面上渲染[MIT]
*  [VUDA](https://github.com/jgbit/vuda)  -提供CUDA运行时API接口的仅标头库.  [麻省理工学院]
*  [Zink](https://gitlab.freedesktop.org/kusma/mesa/tree/zink)  -在Mesa项目的一部分Vulkan之上的OpenGL实现.  [麻省理工学院]
*  [ncnn](https://github.com/Tencent/ncnn)  -带有基于Vulkan的GPU推理的高性能神经网络推理框架.  [BSD 3句]
*  [iMSTK](https://gitlab.kitware.com/iMSTK/iMSTK)  -用于使用Vulkan和VTK后端构建手术模拟的C ++工具包.  [Apache许可2.0]
*  [Quartz](https://github.com/Nadrin/Quartz)  -基于物理的Vulkan RTX路径跟踪器，具有类似于ES7的声明性场景描述语言.  [LGPL-3.0]
*  [VK²](https://github.com/kotlin-graphics/vkk)，Vulkan的Kotlin包装器：代码的表达性和安全性满足图形功能[Apache License 2.0]
*  [small3d](https://www.gamedev.net/projects/515-small3d/)，基于Tiny Vulkan的C ++跨平台游戏开发框架[BSD 3-clause]
*  [VKt/VKh](https://github.com/helixd2s/vkt) ，Vulkan API的工具和帮助程序，基于，并使用C ++ 20.  [麻省理工学院]
*  [Vulkan Kompute](https://github.com/axsaucedo/vulkan-kompute)  -快速，轻巧的Vulkan Compute Framework，针对高级GPU处理用例进行了优化.  [Apache许可2.0]
*  [VKVG](https://github.com/jpbruyere/vkvg) -Vulkan 2D图形库，API遵循与Cairo图形库相同的模式，但具有新功能.
*  [Logi](https://github.com/UL-FRI-LGM/Logi)  -轻量级的面向对象的Vulkan抽象框架.  [BSD 2句]

## Bindings
*  [ash](https://github.com/MaikKlein/ash) 生锈的火山绑定.  [我的]
*  [libvulkan.lua](https://github.com/CapsAdmin/ffibuild/blob/master/vulkan/vulkan.lua) -火山的Lua绑定.
*  [dvulkan](https://github.com/ColonelThirtyTwo/dvulkan) -自动生成的Vulkan D绑定.
*  [ErupteD](https://github.com/ParticlePeter/ErupteD) -Vulkan的另一个自动生成的D绑定.
*  [flextGL](https://github.com/mosra/flextgl) -最小的Vulkan标头/加载器生成器和 [the blog post](http://blog.magnum.graphics/hacking/simple-efficient-vulkan-loading-with-flextgl/) 关于它.
*  [vulkan](https://github.com/expipiplus1/vulkan) -Vulkan和Vulkan内存分配器的Haskell绑定[BSD-3-Clause]
*  [nvk](https://github.com/maierfelix/nvk)  -Vulkan的JavaScript绑定.  [与]
*  [racket-vulkan](https://github.com/zyrolasting/racket-vulkan) -Vulkan的球拍装订 [detailed implementation notes](https://sagegerard.com/racket-vulkan-notes-index.html) .  [与]
*  [Vulkan-hpp](https://github.com/KhronosGroup/Vulkan-Hpp) 开源Vulkan C ++ API源自NVIDIA和 [the blog](https://developer.nvidia.com/open-source-vulkan-c-api) 关于它.
*  [VulkanSharp](https://github.com/mono/VulkanSharp) - C# bindings for Vulkan. [MIT]
*  [Vulkano](https://github.com/vulkano-rs/vulkano)  -围绕Vulkan API的安全且丰富的Rust包装器.  [麻省理工学院]
*  [LWJGL](https://www.lwjgl.org/)  -轻量级Java游戏库3具有Vulkan绑定.  [BSD]
*  [SharpVk](https://github.com/FacticiusVir/SharpVk) - C# bindings for Vulkan with Linq-to-SPIR-V & [NuGet package](https://www.nuget.org/packages/SharpVk) .  [与]
*  [vulkan](https://github.com/realitix/vulkan)  -使用CFFI生成的Vulkan的最终Python绑定.  [Apache许可2.0]
*  [vulkan-go](https://github.com/vulkan-go/vulkan)  -去装订Vulkan.  [我的]
*  [PasVulkan](https://github.com/BeRo1985/pasvulkan) -Vulkan绑定以及对象Pascal的高级包装器库[Zlib]
*  [vulkan-zig](https://github.com/Snektron/vulkan-zig) -Zig的火山粘结发生器[MIT]

## Tools
*  [Nsight™ Visual Studio Edition 5.2+](https://developer.nvidia.com/nvidia-nsight-visual-studio-edition).
*  [LoaderAndValidationLayers](https://github.com/KhronosGroup/Vulkan-LoaderAndValidationLayers)  -来自KhronosGroup.  [Apache许可2.0]
*  [renderdoc](https://github.com/baldurk/renderdoc)  -by baldurk，一种独立的图形调试工具.  [麻省理工学院]
    * [RDCtoVkCpp](https://github.com/azhirnov/RDCtoVkCpp)  -将RenderDoc Vulkan捕获转换为可编译和可执行的C ++代码.  [麻省理工学院]
*  [VulkanTools](https://github.com/LunarG/VulkanTools)  -LunarG的工具，包括图层，“ vktrace”和“ vkreplay”.  [Apache许可2.0]
*  [CodeXL](https://github.com/GPUOpen-Tools/CodeXL)  -CodeXL开源.  [麻省理工学院]
*  [Qualcomm Adreno GPU Tools](https://developer.qualcomm.com/software/adreno-gpu-sdk/tools) -示例，Adreno推荐层，Adreno GPU的最佳实践文档.
*  [Qualcomm Snapdragon Profiler](https://developer.qualcomm.com/software/snapdragon-profiler) -包括Adreno GPU的Vulkan轨迹和帧捕获.
*  [Arm Mobile Studio](https://www.arm.com/products/development-tools/graphics/arm-mobile-studio) -包括可轻松跟踪图形性能问题的Arm图形分析器和Arm Streamline性能分析器，以提供整个系统的性能视图，从而快速确定CPU和GPU上的瓶颈.
*  [Open Capture and Analytics Tool (OCAT)](https://github.com/GPUOpen-Tools/OCAT)  -为D3D11，D3D12和Vulkan提供FPS覆盖和性能测量.  [麻省理工学院]
*  [gapid](https://github.com/google/gapid)  -图形API调试器，可以跟踪和重播Android OpenGL ES和Vulkan应用程序.  [Apache许可2.0]
*  [Arm - PerfDoc](https://github.com/ARM-software/perfdoc)  -针对Mali Application Developer最佳做法文档的验证层.  [麻省理工学院]
*  [glsl_trace](https://github.com/azhirnov/glsl_trace)  -用于Vulkan和OpenGL的着色器调试和性能分析的库.  [麻省理工学院]
*  [MangoHud](https://github.com/flightlessmango/MangoHud)  -Vulkan和OpenGL叠加层，用于监视FPS，温度，CPU / GPU负载.  [麻省理工学院]

## Books
* [Introduction to Computer Graphics and the Vulkan API](https://www.amazon.com/Introduction-Computer-Graphics-Vulkan-API/dp/1548616176) 作者：Kenwright **-使用Vulkan API从彻底的实践角度向读者介绍计算机图形学的令人兴奋的主题.
* [Learning Vulkan](https://www.amazon.com/Learning-Vulkan-Parminder-Singh/dp/1786469804) -通过** Parminder Singh **-使用简单易懂的示例开始使用Vulkan API及其编程技术.
  * [Book's Examples](https://github.com/PacktPublishing/Learning-Vulkan)
* [Vulkan Cookbook](https://www.amazon.com/Vulkan-Cookbook-Pawel-Lapinski/dp/1786468158)-作者：Pawel Lapinski **-探索各种图形编程和GPU计算方法，以充分利用Vulkan API.
  * [Book's Examples](https://github.com/PacktPublishing/Vulkan-Cookbook)
* [Vulkan Programming Guide](https://www.amazon.com/Vulkan-Programming-Guide-Official-Learning/dp/0134464540) -由** Graham Sellers **和** John Kessenich **撰写-为许多领域引入了强大的3D开发技术.

## Khronos
*规格
    *  [Vulkan 1.0 Specification](https://www.khronos.org/registry/vulkan/specs/1.0/pdf/vkspec.pdf)
    *  [Vulkan 1.0 Specification with Extensions ](https://www.khronos.org/registry/vulkan/specs/1.0-extensions/pdf/vkspec.pdf)
    *  [Vulkan 1.0 Specification with WSI Extensions](https://www.khronos.org/registry/vulkan/specs/1.0-wsi_extensions/pdf/vkspec.pdf)
    *  [Vulkan 1.1 Specification](https://www.khronos.org/registry/vulkan/specs/1.1/pdf/)
    *  [Vulkan 1.1 Specification with Extensions ](https://www.khronos.org/registry/vulkan/specs/1.1-extensions/pdf/vkspec.pdf)
    *  [Vulkan 1.1 Specification with KHR Extensions](https://www.khronos.org/registry/vulkan/specs/1.1-khr-extensions/pdf/)
    *  [Vulkan 1.2 Specification](https://www.khronos.org/registry/vulkan/specs/1.2/pdf/vkspec.pdf)
    *  [Vulkan 1.2 Specification with Extensions ](https://www.khronos.org/registry/vulkan/specs/1.2-extensions/pdf/vkspec.pdf)
    *  [Vulkan 1.2 Specification with KHR Extensions](https://www.khronos.org/registry/vulkan/specs/1.2-khr-extensions/pdf/vkspec.pdf)
*快速参考表
    *  [Vulkan 1.0 Quick Reference Sheets](https://www.khronos.org/registry/vulkan/specs/1.0/refguide/Vulkan-1.0-web.pdf)
    *  [Vulkan 1.1 Quick Reference Sheets](https://www.khronos.org/registry/vulkan/specs/1.1/refguide/Vulkan-1.1-web.pdf)
*  [Conformance Tests (CTS)](https://github.com/KhronosGroup/Vulkan-CTS)
*会议和演讲
    *  [GDC 2016 Presentations](https://www.khronos.org/developers/library/2016-gdc)
    *  [2016 UK Chapter: Moving to Vulkan](https://www.khronos.org/developers/library/2016-uk-chapter-moving-to-vulkan)
    *  [SIGGRAPH 2016 BOF - Vulkan](https://www.youtube.com/watch?v=CsHMiEQgrLA)
    *  [SIGGRPAH 2016 Best Practices Roundtable](https://www.youtube.com/watch?v=owuJRPKIUAg)
    *  [2016 Vulkan DevDay UK](https://www.khronos.org/developers/library/2016-vulkan-devday-uk)
    *  [2016 Vulkan DevDay Seoul](https://www.khronos.org/developers/library/2016-Vulkan-DevU-Seoul)
    *  [2017 Vulkan DevU Vancouver](https://www.khronos.org/developers/library/2017-vulkan-devu-vancouver)
    *  [2017 Vulkan Loader Webinar](https://www.khronos.org/developers/library/2017-vulkan-loader-webinar)
    *  [SIGGRAPH 2017 BOF - Vulkan](https://www.youtube.com/watch?v=Nx0u-9ZwrmQ)
    *  [2018 Vulkan Montreal Dev Day](https://www.khronos.org/developers/library/2018-vulkan-montreal-dev-day)
    *  [2018 Vulkanised!](https://www.khronos.org/developers/library/2018-vulkanised)
    *  [SIGGRAPH 2018 BOF - Vulkan](https://www.youtube.com/watch?v=FCAM-3aAzXg&t=18350s)

## Community
*  [Freenode IRC](http://webchat.freenode.net/?channels=Vulkan)
*  [Google Plus](https://plus.google.com/communities/108983304183191634377)
*  [Khronos Forum](https://forums.khronos.org/forumdisplay.php/114-Vulkan)
*  [Reddit](https://www.reddit.com/r/vulkan/)
*  [Stack Overflow](http://stackoverflow.com/questions/tagged/vulkan)
*  [Discord](https://discord.com/invite/tFdvbEj)

## Related lists
*  [awesome](https://github.com/sindresorhus/awesome) -超赞列表的精选列表.
*  [awesome-opengl](https://github.com/eug/awesome-opengl) -精选的很棒的OpenGL库，调试器和资源列表.
*  [gamedev](https://github.com/ellisonleao/magictools) -有关游戏开发的真棒列表.
*  [graphics-resources](https://github.com/mattdesl/graphics-resources) -图形编程资源列表.
*  [awesome-d3d12](https://github.com/vinjn/awesome-d3d12) -精选的D3D12库，调试器和资源的清单.

## License

[![Creative Commons License](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

这项工作是根据 [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

## Contributing
请参阅 [CONTRIBUTING](https://github.com/vinjn/awesome-vulkan/blob/master/CONTRIBUTING.md) 有关详细信息.
