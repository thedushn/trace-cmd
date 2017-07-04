cmake_minimum_required(VERSION 3.7)
project(trace_cmd_source)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} python")
find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)
target_link_libraries(Python.h ${PYTHON_LIBRARIES})
set(SOURCE_FILES
        include/linux/string.h
        include/linux/time64.h
        bug.h
        cpu.h
        ctracecmd.i
        ctracecmd_wrap.c
        ctracecmdgui.i
        event-parse.c
        event-parse.h
        event-plugin.c
        event-utils.h
        kbuffer-parse.c
        kbuffer.h
        kernel-shark.c
        kernel-shark.h
        ks_version.h
        kshark-plugin.h
        list.h
        parse-filter.c
        parse-utils.c
        plugin_blk.c
        plugin_cfg80211.c
        plugin_function.c
        plugin_hrtimer.c
        plugin_jbd2.c
        plugin_kmem.c
        plugin_kvm.c
        plugin_mac80211.c
        plugin_python.c
        plugin_sched_switch.c
        plugin_scsi.c
        plugin_tlb.c
        plugin_xen.c
        str_error_r.c
        tc_version.h
        trace-blk-hack.c
        trace-capture.c
        trace-capture.h
        trace-check-events.c
        trace-cmd-local.h
        trace-cmd.c
        trace-cmd.h
        trace-compat.c
        trace-compat.h
        trace-dialog.c
        trace-filter-hash.c
        trace-filter-hash.h
        trace-filter.c
        trace-filter.h
        trace-ftrace.c
        trace-graph-main.c
        trace-graph.c
        trace-graph.h
        trace-gui.h
        trace-hash-local.h
        trace-hash.c
        trace-hash.h
        trace-hist.c
        trace-hooks.c
        trace-input.c
        trace-list.c
        trace-listen.c
        trace-local.h
        trace-mem.c
        trace-msg.c
        trace-msg.h
        trace-output.c
        trace-plot-cpu.c
        trace-plot-task.c
        trace-plot.c
        trace-profile.c
        trace-read.c
        trace-record.c
        trace-recorder.c
        trace-restore.c
        trace-seq.c
        trace-show.c
        trace-snapshot.c
        trace-split.c
        trace-stack.c
        trace-stat.c
        trace-stream.c
        trace-usage.c
        trace-util.c
        trace-view-main.c
        trace-view-store.c
        trace-view-store.h
        trace-view.c
        trace-view.h
        trace-xml.c
        trace-xml.h
        version.h)
include(FindGTK2)
if (GTK2_FOUND)
    include_directories(${GTK2_INCLUDE_DIRS})
    link_directories(${GTK2_LIBRARY_DIRS})
    link_libraries(${GTK2_LIBRARIES})
endif (GTK2_FOUND)


    include_directories(${GTK3_INCLUDE_DIRS})
    link_directories(${GTK3_LIBRARY_DIRS})
    link_libraries(${GTK3_LIBRARIES})

add_executable(trace_cmd_source ${SOURCE_FILES})