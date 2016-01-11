

include_HEADERS = include/FreeRTOS.h \
									include/FreeRTOSConfig.h \
									include/list.h \
									include/queue.h \
									include/task.h \
									include/timers.h \
									include/croutine.h \
									include/projdefs.h \
									include/portable.h \
									include/deprecated_definitions.h \
									include/event_groups.h \
									include/mpu_wrappers.h \
									include/semphr.h \
									include/StackMacros.h

									

lib_LTLIBRARIES = libfreertos_avr.la

libfreertos_avr_la_CFLAGS = -I../include 

libfreertos_avr_la_SOURCES = \
							source/croutine.c \
							source/tasks.c	  \
							source/event_groups.c 	\
							source/list.c     \
							source/queue.c    \
							source/timers.c



