cmake_minimum_required(VERSION 3.3)
project(wifidog_gateway)

include_directories(./ ./src libhttpd)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES
    libhttpd/api.c
    libhttpd/httpd.h
    libhttpd/httpd_priv.h
    libhttpd/ip_acl.c
    libhttpd/protocol.c
    libhttpd/version.c
    src/auth.c
    src/auth.h
    src/centralserver.c
    src/centralserver.h
    src/client_list.c
    src/client_list.h
    src/commandline.c
    src/commandline.h
    src/common.h
    src/conf.c
    src/conf.h
    src/debug.c
    src/debug.h
    src/firewall.c
    src/firewall.h
    src/fw_iptables.c
    src/fw_iptables.h
    src/gateway.c
    src/gateway.h
    src/http.c
    src/http.h
    src/httpd_thread.c
    src/httpd_thread.h
    src/main.c
    src/ping_thread.c
    src/ping_thread.h
    src/pstring.c
    src/pstring.h
    src/safe.c
    src/safe.h
    src/simple_http.c
    src/simple_http.h
    src/util.c
    src/util.h
    src/wd_util.c
    src/wd_util.h
    src/wdctl_thread.c
    src/wdctl_thread.h)

set(SOURCE_FILES_WDCTL
        libhttpd/api.c
        libhttpd/httpd.h
        libhttpd/httpd_priv.h
        libhttpd/ip_acl.c
        libhttpd/protocol.c
        libhttpd/version.c
        src/auth.c
        src/auth.h
        src/centralserver.c
        src/centralserver.h
        src/client_list.c
        src/client_list.h
        src/commandline.c
        src/commandline.h
        src/common.h
        src/conf.c
        src/conf.h
        src/debug.c
        src/debug.h
        src/firewall.c
        src/firewall.h
        src/fw_iptables.c
        src/fw_iptables.h
        src/gateway.c
        src/gateway.h
        src/http.c
        src/http.h
        src/httpd_thread.c
        src/httpd_thread.h
        src/ping_thread.c
        src/ping_thread.h
        src/pstring.c
        src/pstring.h
        src/safe.c
        src/safe.h
        src/simple_http.c
        src/simple_http.h
        src/util.c
        src/util.h
        src/wd_util.c
        src/wd_util.h
        src/wdctl_thread.c
        src/wdctl_thread.h
        src/wdctl.h
        src/wdctl.c)

link_libraries(cyassl)
add_executable(wifidog_gateway ${SOURCE_FILES})
add_executable(wdctl ${SOURCE_FILES_WDCTL})

