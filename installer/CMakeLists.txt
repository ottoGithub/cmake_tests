cmake_minimum_required(VERSION 3.8.0)
 
if(EXISTS "${CMAKE_ROOT}/Modules/CPack.cmake")
	include(InstallRequiredSystemLibraries)
	 
	set(CPACK_SET_DESTDIR "on")
	set(CPACK_PACKAGING_INSTALL_PREFIX "/tmp")
	 
	set(CPACK_PACKAGE_DESCRIPTION "Fractal Generation Library")
	set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Fractal Generation Library")
	set(CPACK_PACKAGE_VENDOR "testerson-mactesterface")
	set(CPACK_PACKAGE_CONTACT "testerson-mactesterface@mail.com")
	set(CPACK_PACKAGE_VERSION_MAJOR "${PROJECT_VERSION_MAJOR}")
	set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
	set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")
	set(CPACK_PACKAGE_FILE_NAME "${CMAKE_PROJECT_NAME}_${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}")
	set(CPACK_SOURCE_PACKAGE_FILE_NAME "${CMAKE_PROJECT_NAME}_${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}")
	 
	set(CPACK_DEBIAN_PACKAGE_DEPENDS "libc6 (>= 2.1.3), libgcc1 (>= 1:4.1.1), libstdc++6 (>= 4.2.1)")
	 
	set(CPACK_DEBIAN_PACKAGE_PRIORITY "optional")
	set(CPACK_DEBIAN_PACKAGE_SECTION "kde")
	set(CPACK_DEBIAN_ARCHITECTURE ${CMAKE_SYSTEM_PROCESSOR})
	 
	set(CPACK_COMPONENTS_ALL Libraries ApplicationData)

	include(CPack)
endif()
