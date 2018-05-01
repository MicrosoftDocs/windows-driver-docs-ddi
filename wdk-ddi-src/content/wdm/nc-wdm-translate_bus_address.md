---
UID: NC:wdm.TRANSLATE_BUS_ADDRESS
title: TRANSLATE_BUS_ADDRESS
author: windows-driver-content
description: The TranslateBusAddress routine translates addresses on the parent bus to logical addresses.
old-location: kernel\translatebusaddress.htm
old-project: kernel
ms.assetid: DDED1237-74B7-4127-8E86-D0794A1FB49B
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: TRANSLATE_BUS_ADDRESS, TranslateBusAddress, TranslateBusAddress routine [Kernel-Mode Driver Architecture], drvr_interface_68887adb-724b-47ca-80e6-b8b934ae2414.xml, kernel.bustranslatebusaddress, kernel.translatebusaddress, wdm/TranslateBusAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	TranslateBusAddress
product: Windows
targetos: Windows
req.typenames: 
---

# TRANSLATE_BUS_ADDRESS callback function


## -description


The <i>TranslateBusAddress</i> routine translates addresses on the parent bus to logical addresses.


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540707">BUS_INTERFACE_STANDARD</a> structure for the interface.


### -param BusAddress [in]

The bus-relative address to be translated.


### -param Length [in]

The length, in bytes, of the input memory that <i>BusAddress</i> points to.


### -param AddressSpace [in, out]

On input, the address space in which the device's hardware address resides. A value of 0x0 signifies memory space, and a value of 0x1 signifies port I/O space. On output, <i>AddressSpace</i> indicates the address space in which the <i>TranslatedAddress</i> resides.


### -param TranslatedAddress [out]

The translated (logical) address that corresponds to the bus-relative address that the caller provides in <i>BusAddress</i>.


## -returns



The 
      <i>TranslateBusAddress</i> routine returns <b>TRUE</b> if the translation operation succeeded and <b>FALSE</b> otherwise.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540707">BUS_INTERFACE_STANDARD</a>
 

 

