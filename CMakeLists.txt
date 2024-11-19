cmake_minimum_required(VERSION 3.16)

project(QAMQP VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 6.5 REQUIRED COMPONENTS Core Network)

qt_standard_project_setup(REQUIRES 6.5)

add_library(QAMQP STATIC
    src/qamqpauthenticator.cpp
    src/qamqpauthenticator.h
    src/qamqpchannel.cpp
    src/qamqpchannel.h
    src/qamqpchannel_p.h
    src/qamqpchannelhash.cpp
    src/qamqpchannelhash_p.h
    src/qamqpclient.cpp
    src/qamqpclient.h
    src/qamqpclient_p.h
    src/qamqpexchange.cpp
    src/qamqpexchange.h
    src/qamqpexchange_p.h
    src/qamqpframe.cpp
    src/qamqpframe_p.h
    src/qamqpglobal.h
    src/qamqpmessage.cpp
    src/qamqpmessage.h
    src/qamqpmessage_p.h
    src/qamqpqueue.cpp
    src/qamqpqueue.h
    src/qamqpqueue_p.h
    src/qamqptable.cpp
    src/qamqptable.h
)

target_compile_definitions(QAMQP PRIVATE GIT_VERSION="1.0")

target_link_libraries(QAMQP PRIVATE Qt6::Core Qt6::Network)

target_include_directories(QAMQP INTERFACE src)
