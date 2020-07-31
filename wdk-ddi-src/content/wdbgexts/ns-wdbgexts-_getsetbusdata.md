---
UID: NS:wdbgexts._GETSETBUSDATA
title: _GETSETBUSDATA (wdbgexts.h)
description: The IG_GET_BUS_DATA Ioctl operation reads data from a system bus and the IG_SET_BUS_DATA Ioctl operation writes data to a system bus.
old-location: debugger\ig_get_bus_data.htm
tech.root: debugger
ms.assetid: aca1fe96-20c7-4a51-a331-583b107f62e0
ms.date: 05/03/2018
keywords: ["_GETSETBUSDATA structure"]
ms.keywords: "*PBUSDATA, BUSDATA, BUSDATA structure [Windows Debugging], GETSETBUSDATA, GETSETBUSDATA structure [Windows Debugging], PBUSDATA, PBUSDATA structure pointer [Windows Debugging], WdbgExts_Ref_090ca26a-5955-40c6-82c3-310a02a9d64d.xml, _GETSETBUSDATA, debugger.ig_get_bus_data, wdbgexts/GETSETBUSDATA, wdbgexts/PBUSDATA"
f1_keywords:
 - "wdbgexts/BUSDATA"
 - "BUSDATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- BUSDATA
targetos: Windows
req.typenames: BUSDATA, *PBUSDATA
---

# _GETSETBUSDATA structure


## -description


The IG_GET_BUS_DATA <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a> operation reads data from a system bus and the IG_SET_BUS_DATA <b>Ioctl</b> operation writes data to a system bus.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_GET_BUS_DATA or IG_SET_BUS_DATA, <i>IpvData</i> should contain an instance of the BUSDATA structure.
  


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



The parameters for the IG_GET_BUS_DATA and IG_SET_BUS_DATA <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a> operations are the members of the BUSDATA structure.

This operation is only available in kernel-mode debugging.

The properties of the data in the bus depends on the system, bus, and slot.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a>
 

 

