# Copyright (c) 2016 - present Facebook, Inc.
# All rights reserved.
#
# This source code is licensed under the BSD style license found in the
# LICENSE file in the root directory of this source tree. An additional grant
# of patent rights can be found in the PATENTS file in the same directory.

TESTS_DIR = ../../..

IPHONESIMULATOR_ISYSROOT_SUFFIX = /Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator.sdk

XCODEROOT = $(shell $(XCODE_SELECT) -p)

CLANG_OPTIONS = -x objective-c \
  -isysroot $(XCODEROOT)$(IPHONESIMULATOR_ISYSROOT_SUFFIX) \
  -mios-simulator-version-min=8.2 --target=x86_64-apple-darwin14 -fobjc-arc -c \

ANALYZER = linters
INFER_OPTIONS = --no-filtering --debug-exceptions --project-root $(TESTS_DIR) \
--iphoneos-target-sdk-version 8.0 \
--iphoneos-target-sdk-version-skip-path "codetoanalyze/objc/ioslints/filter_out_unavailable_api\.m" \
--no-keep-going
INFERPRINT_OPTIONS = --issues-tests

SOURCES = \
  $(wildcard *.m) \
  $(wildcard */*.m) \

include $(TESTS_DIR)/clang.make
