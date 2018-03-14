---
UID: NC:hdaudio.PGET_WALL_CLOCK_REGISTER
title: PGET_WALL_CLOCK_REGISTER
author: windows-driver-content
description: The GetWallClockRegister routine retrieves a pointer to the wall clock register.The function pointer type for a GetWallClockRegister routine is defined as follows.
old-location: audio\getwallclockregister.htm
old-project: audio
ms.assetid: 4efe4b23-eb4f-4170-8d73-05cae2ba21c2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetWallClockRegister, GetWallClockRegister callback function [Audio Devices], PGET_WALL_CLOCK_REGISTER, aud-prop2_1600e03f-4be0-4a61-9596-7970ace3df2f.xml, audio.getwallclockregister, hdaudio/GetWallClockRegister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	GetWallClockRegister
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PGET_WALL_CLOCK_REGISTER callback


## -description


The <code>GetWallClockRegister</code> routine retrieves a pointer to the wall clock register.

The function pointer type for a <code>GetWallClockRegister</code> routine is defined as follows.


## -prototype


````
PGET_WALL_CLOCK_REGISTER GetWallClockRegister;

VOID GetWallClockRegister(
  _In_  PVOID  _context,
  _Out_ PULONG *Wallclock
)
{ ... }
````


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param *Wallclock [out]

Retrieves a pointer to the wall clock register. This parameter points to a caller-allocated PULONG variable into which the routine writes a pointer to the register. The HD Audio bus driver maps the register to a system virtual address that is accessible to the function driver.


## -returns



None




## -remarks



For more information, see <a href="https://msdn.microsoft.com/6764affc-a4f0-4568-aa27-7f12e86b818b">Wall Clock and Link Position Registers</a>.




## -see-also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



 

 


