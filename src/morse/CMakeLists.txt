
if(BUILD_CORE_SUPPORT)
INSTALL(FILES __init__.py #init_middleware.py
        DESTINATION ${PYTHON_INSTDIR}/morse
        )

INSTALL(DIRECTORY core actuators geolandloader helpers blender sensors robots builder
        DESTINATION ${PYTHON_INSTDIR}/morse
        REGEX .*py.$ EXCLUDE
        )

ADD_SUBDIRECTORY(modifiers)
endif()

ADD_SUBDIRECTORY(middleware)
