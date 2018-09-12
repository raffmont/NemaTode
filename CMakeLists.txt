cmake_minimum_required(VERSION 3.5)
project(nematode)

set(CMAKE_CXX_STANDARD 11)

# TODO: https://developer.android.com/ndk/guides/cmake

# Include the support to external projects
include(ExternalProject)

# Set the external install location
set(EXTERNAL_INSTALL_LOCATION ${CMAKE_BINARY_DIR}/external)

# Add to the includes
include_directories(SYSTEM ${EXTERNAL_INSTALL_LOCATION}/include)

# Add to the libraries
link_directories(${EXTERNAL_INSTALL_LOCATION}/lib)

include_directories(SYSTEM include)

# Add the executables to the project
add_executable(
        ${PROJECT_NAME}
        demo_advanced.cpp
        include/nmeaparse/Event.h
        include/nmeaparse/GPSFix.h
        include/nmeaparse/GPSService.h
        include/nmeaparse/nmea.h
        include/nmeaparse/NMEACommand.h
        include/nmeaparse/NMEAParser.h
        include/nmeaparse/NumberConversion.h
        src/GPSFix.cpp
        src/GPSService.cpp
        src/NMEACommand.cpp
        src/NMEAParser.cpp
        src/NumberConversion.cpp
)
