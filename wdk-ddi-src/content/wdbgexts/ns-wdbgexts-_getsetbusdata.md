---
UID: NS:wdbgexts._GETSETBUSDATA
title: _GETSETBUSDATA
author: windows-driver-content
description: The IG_GET_BUS_DATA Ioctl operation reads data from a system bus and the IG_SET_BUS_DATA Ioctl operation writes data to a system bus.
old-location: debugger\ig_get_bus_data.htm
old-project: debugger
ms.assetid: aca1fe96-20c7-4a51-a331-583b107f62e0
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GETSETBUSDATA structure [Windows Debugging], GETSETBUSDATA, PBUSDATA structure pointer [Windows Debugging], wdbgexts/PBUSDATA, WdbgExts_Ref_090ca26a-5955-40c6-82c3-310a02a9d64d.xml, BUSDATA structure [Windows Debugging], _GETSETBUSDATA, PBUSDATA, BUSDATA, debugger.ig_get_bus_data, *PBUSDATA, wdbgexts/GETSETBUSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Windows
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wdbgexts.h
apiname: 
-	BUSDATA
product: Windows
targetos: Windows
req.typenames: *PBUSDATA, BUSDATA
req.product: Windows 10 or later.
---

# _GETSETBUSDATA structure


## -description


The IG_GET_BUS_DATA <a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a> operation reads data from a system bus and the IG_SET_BUS_DATA <b>Ioctl</b> operation writes data to a system bus.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_GET_BUS_DATA or IG_SET_BUS_DATA, <i>IpvData</i> should contain an instance of the BUSDATA structure.
  


## -syntax


````
typedef struct _GETSETBUSDATA {
  ULONG BusDataType;
  ULONG BusNumber;
  ULONG SlotNumber;
  PVOID Buffer;
  ULONG Offset;
  ULONG Length;
} BUSDATA, *PBUSDATA;
````


## -struct-fields




### -field BusDataType

Specifies the bus data type to use.  For details of allowed values, see the documentation for the BUS_DATA_TYPE enumeration in the Platform SDK.


### -field BusNumber

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same bus data type.


### -field SlotNumber

Specifies the logical slot number on the bus.


### -field Buffer

Specifies the buffer that contains the memory to write to the bus, or to receive the memory that is read from the bus.

The size of <b>Buffer</b> must be at least the value of <b>Length</b>.


### -field Offset

Specifies the offset in the bus data to start reading from or writing to.


### -field Length

Specifies the number of bytes to read from or write to the bus when the <b>Ioctl</b> operation is called.  Upon returning, <b>Length</b> is set to the number of bytes actually read or written.


## -remarks


The parameters for the IG_GET_BUS_DATA and IG_SET_BUS_DATA <a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a> operations are the members of the BUSDATA structure.

This operation is only available in kernel-mode debugging.

The properties of the data in the bus depends on the system, bus, and slot.



## -see-also

<a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20GETSETBUSDATA structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

