---
UID: NS:61883._BUS_RESET_NOTIFY
title: "_BUS_RESET_NOTIFY"
author: windows-driver-content
description: This structure is used to register or deregister the PBUS_RESET_ROUTINE callback.
old-location: ieee\bus_reset_notify.htm
old-project: IEEE
ms.assetid: 9CF14B12-D94F-486D-A5FC-E7CC2730D8E9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBUS_RESET_NOTIFY, 61883/BUS_RESET_NOTIFY, 61883/PBUS_RESET_NOTIFY, BUS_RESET_NOTIFY, BUS_RESET_NOTIFY structure [Buses], IEEE.bus_reset_notify, PBUS_RESET_NOTIFY, PBUS_RESET_NOTIFY structure pointer [Buses], _BUS_RESET_NOTIFY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	BUS_RESET_NOTIFY
product: Windows
targetos: Windows
req.typenames: BUS_RESET_NOTIFY, *PBUS_RESET_NOTIFY
---

# _BUS_RESET_NOTIFY structure


## -description


This structure is used to register or deregister the <a href="https://msdn.microsoft.com/99555765-A58F-45A1-B146-3742C390E666">PBUS_RESET_ROUTINE</a> callback. The request registers the caller to be notified when a reset of the 1394 bus occurs or cancels a previous registration. When the registered callback (bus reset) routine is called, the updated generation count and node address will be specified in parameter <b>BusResetInfo</b>. If a driver registers for bus-reset notification, it must cancel registration before the system unloads the driver.


## -struct-fields




### -field Flags

The caller sets this member to REGISTER_BUS_RESET_NOTIFY to register to receive bus-reset notifications, or to DEREGISTER_BUS_RESET_NOTIFY to stop receiving bus-reset notifications.


### -field pfnNotify

Pointer to a caller-supplied function to be called by the protocol driver when the 1394 bus is reset. 

This function uses the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Void
  (*PBUS_RESET_ROUTINE)( 
 IN PVOID  Context; 
 IN PBUS_GENERATION_NODE  BusResetInfo;
 );</pre>
</td>
</tr>
</table></span></div>

### -field Context

Pointer to a caller-defined context for the function at <b>pfnNotify</b>. The IEC-61883 protocol driver calls this function after a reset of the 1394 bus.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

