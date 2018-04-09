# WARNING
BoardConfig.mk doesn't contain PARTITION_SIZE values, which have to be added manually in this directory:
"device/lge/*your-specific-lgg5-device*/BoardConfig.mk"

## Why should I do it manually?
Different LG G5 devices doesn't have the same PARTITION_SIZE values.

## Instruction
Simply paste these lines in "device/lge/*your-specific-lgg5-device*/BoardConfig.mk"
and fill them with the correct partition value.
```
BOARD_BOOTIMAGE_PARTITION_SIZE := *my_bootimage_partition_size*
BOARD_CACHEIMAGE_PARTITION_SIZE := 
BOARD_PERSISTIMAGE_PARTITION_SIZE := 
BOARD_RECOVERYIMAGE_PARTITION_SIZE := 
BOARD_SYSTEMIMAGE_PARTITION_SIZE := 
BOARD_USERDATAIMAGE_PARTITION_SIZE :=
```
#How do I get the correct partition value?
Open your terminal (TWRP is fine) and enter:
```
blockdev --getsize64 /dev/block/bootdevice/by-name/*every_partition_you_need*
```
