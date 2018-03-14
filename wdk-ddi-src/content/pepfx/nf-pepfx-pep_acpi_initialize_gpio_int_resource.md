---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE
title: PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_gpio_int_resource.htm
old-project: kernel
ms.assetid: EF8E3D1D-9C87-4083-A022-FD888D370B20
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE, PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_gpio_int_resource, pepfx/PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a> structure.


## -syntax


````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE(
  _In_  KINTERRUPT_MODE      InterruptType,
  _In_  KINTERRUPT_POLARITY  LevelType,
  _In_  BOOLEAN              Shareable,
  _In_  BOOLEAN              CanWake,
  _In_  GPIO_PIN_CONFIG_TYPE PinConfig,
  _In_  USHORT               DebounceTimeout,
  _In_  UCHAR                ResourceSourceIndex,
  _In_  PUNICODE_STRING      ResourceSourceName,
  _In_  BOOLEAN              ResourceUsage,
  _In_  PUCHAR               VendorData,
  _In_  USHORT               VendorDataLength,
  _In_  PUSHORT              PinTable,
  _In_  UCHAR                PinCount,
  _Out_ PPEP_ACPI_RESOURCE   Resource
);
````


## -parameters




### -param InterruptType [in]

A <a href="..\wudfwdm\ne-wudfwdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.


### -param LevelType [in]

A <a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.


### -param Shareable [in]

Indicates if the device can be shared.


### -param CanWake [in]

Indicates if the device can be woken from a low-power state.


### -param PinConfig [in]

A <a href="..\pepfx\ne-pepfx-_gpio_pin_config_type.md">GPIO_PIN_CONFIG_TYPE</a> enumeration value that identifies the GPIO pin configuration type.


### -param DebounceTimeout [in]

Specifies the hardware debounce wait time, in hundredths of milliseconds.


### -param ResourceSourceIndex [in]

This parameter should always be zero.


### -param ResourceSourceName [in]

This parameter should always be "ResourceConsumer."


### -param ResourceUsage [in]

Indicates if this device is in use.


### -param VendorData [in]

A pointer to a raw data buffer containing vendor-defined byte data to be decoded by the OS driver. 


### -param VendorDataLength [in]

The size of the buffer in the <i>VendorData</i> partameter.


### -param PinTable [in]

A list of pin numbers on the resource. 


### -param PinCount [in]

The number of pins described by the <i>PinTable</i> parameter.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a>. 


## -returns



This function does not return a value.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a>



<a href="..\wudfwdm\ne-wudfwdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>



<a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>



<a href="..\pepfx\ne-pepfx-_gpio_pin_config_type.md">GPIO_PIN_CONFIG_TYPE</a>



 

 


