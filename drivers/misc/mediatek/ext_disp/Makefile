PLATFORM := $(subst ",,$(CONFIG_MTK_PLATFORM))
PLATFORM := $(strip $(PLATFORM))

ifeq ($(PLATFORM),)
PLATFORM := mt8167
endif

ccflags-y += -I$(srctree)/drivers/misc/mediatek/ext_disp/include
ccflags-y += -I$(srctree)/drivers/misc/mediatek/ext_disp/mt8167

ifeq ($(CONFIG_SINGLE_PANEL_OUTPUT),y)
else ifneq ($(wildcard $(srctree)/drivers/misc/mediatek/ext_disp/$(PLATFORM)/),)
ifneq ($(PLATFORM), mt6739)
obj-y += $(PLATFORM)/
obj-y += common/
else
obj-y += dummy/
endif
else
obj-y += dummy/
endif
