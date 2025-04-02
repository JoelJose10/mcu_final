################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (13.3.rel1)
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include X-CUBE-AI/App/subdir.mk
-include Drivers/STM32F7xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

OPTIONAL_TOOL_DEPS := \
$(wildcard ../makefile.defs) \
$(wildcard ../makefile.init) \
$(wildcard ../makefile.targets) \

BUILD_ARTIFACT_NAME := mcu_final
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
mcu_final.elf \

MAP_FILES += \
mcu_final.map \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
mcu_final.list \

# All Target
all: main-build

# Main-build Target
main-build: mcu_final.elf secondary-outputs

# Define Linker Flags with printf() support
LDFLAGS = -mcpu=cortex-m7 \
          -T"C:\Users\joelj\STM32CubeIDE\workspace_1.17.0\mcu_final\STM32F723IEKX_FLASH.ld" \
          -Wl,-Map="mcu_final.map" -Wl,--gc-sections \
          -mfpu=fpv5-sp-d16 -mfloat-abi=hard -mthumb \
          -Wl,--start-group -lc -lm -Wl,--end-group \
          --specs=nano.specs  # ✅ Enables printf() support

mcu_final.elf: $(OBJS) $(USER_OBJS)
	arm-none-eabi-gcc -o "mcu_final.elf" @"objects.list" $(USER_OBJS) $(LIBS) $(LDFLAGS)
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

mcu_final.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "mcu_final.list"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) default.size.stdout mcu_final.elf mcu_final.list mcu_final.map
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST)

fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

.PHONY: all clean dependents main-build fail-specified-linker-script-missing warn-no-linker-script-specified

-include ../makefile.targets
