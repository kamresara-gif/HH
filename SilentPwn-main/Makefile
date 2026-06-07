ARCHS = arm64
TARGET = iphone:clang:latest:14.0

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = SilentPwn

SilentPwn_FILES = Tweak.mm $(wildcard Source/UI/*.mm)
SilentPwn_FRAMEWORKS = UIKit Foundation QuartzCore
SilentPwn_CFLAGS = -fobjc-arc -Wno-deprecated-declarations -Wno-unused-variable -Wno-unused-value

include $(THEOS_MAKE_PATH)/tweak.mk
