# Copyright (c) 2007-2014, Lloyd Hilaiel <me@lloyd.io>
#
# Permission to use, copy, modify, and/or distribute this software for any
# purpose with or without fee is hereby granted, provided that the above
# copyright notice and this permission notice appear in all copies.
#
# THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
# WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
# MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
# ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
# WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
# ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
# OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

SET (SRCS perftest.c documents.c documents.h)

INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/include ${CMAKE_SOURCE_DIR}/include)

ADD_EXECUTABLE(perftest ${SRCS})

IF (DISABLE_SHARED)
  TARGET_LINK_LIBRARIES(perftest yajl_s)
ELSE (DISABLE_SHARED)
  TARGET_LINK_LIBRARIES(perftest yajl)
ENDIF (DISABLE_SHARED)

ADD_DEPENDENCIES (perftest src)

# vim: ts=2 sw=2 et:
