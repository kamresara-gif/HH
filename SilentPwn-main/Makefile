# --- إعدادات البناء (من القديم والجديد) ---
ARCHS = arm64
TARGET = iphone:clang:latest:14.0
DEBUG = 0
FINALPACKAGE = 1
FOR_RELEASE = 1

include $(THEOS)/makefiles/common.mk

# --- اسم المشروع (من القديم والجديد) ---
TWEAK_NAME = SilentPwn

# --- الربط والمكتبات (الجزء الأهم الذي تحتاجه من القديم) ---
SilentPwn_FRAMEWORKS = UIKit Foundation Security QuartzCore CoreText
# تأكد من المسارات أدناه إذا كنت تستخدم مكتبات خارجية مثل Keystone أو JRMemory
SilentPwn_LDFLAGS += -F. -framework JRMemory
SilentPwn_CCFLAGS = -std=c++11 -fno-rtti -fno-exceptions -DNDEBUG
SilentPwn_CFLAGS = -fobjc-arc -Wno-deprecated-declarations -Wno-unused-variable -Wno-unused-value

# --- ملفات المشروع (هنا يحدث الدمج الحقيقي) ---
# ندمج ملف Tweak.mm مع المسارات الجديدة لمجلد Source
SilentPwn_FILES = Tweak.mm $(wildcard Source/UI/*.mm) $(wildcard Source/Memory/*.mm)

include $(THEOS_MAKE_PATH)/tweak.mk
