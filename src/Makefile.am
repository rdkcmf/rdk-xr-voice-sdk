##########################################################################
# If not stated otherwise in this file or this component's LICENSE
# file the following copyright and licenses apply:
#
# Copyright 2019 RDK Management
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
##########################################################################
include_HEADERS = xr_voice_sdk.h
lib_LTLIBRARIES = libxr-voice-sdk.la

libxr_voice_sdk_la_SOURCES = vsdk_version.h \
                             vsdk.c

BUILT_SOURCES = vsdk_version.h
CLEANFILES    = vsdk_version.h

vsdk_version.h:
	echo "#define VSDK_VER_MAJOR \"1\"" >$@
	echo "#define VSDK_VER_MINOR \"`git -C ${srcdir} rev-list --count 5ef25cd0850bb2fcf94cdb7f73c7dabce0131ffd..HEAD``git -C ${srcdir} diff --quiet || echo \"++\"`\"" >>$@
	echo "#define VSDK_BRANCH    \"${GIT_BRANCH}\"" >>$@
	echo "#define VSDK_COMMIT_ID \"`git -C ${srcdir} log --format="%H" -n 1`\"" >>$@
	echo "#define VSDK_VERSION (VSDK_VER_MAJOR \".\" VSDK_VER_MINOR)" >>$@
