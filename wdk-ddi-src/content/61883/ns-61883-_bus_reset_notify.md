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
ms.keywords: 61883/BUS_RESET_NOTIFY, BUS_RESET_NOTIFY, PBUS_RESET_NOTIFY, IEEE.bus_reset_notify, PBUS_RESET_NOTIFY structure pointer [Buses], *PBUS_RESET_NOTIFY, BUS_RESET_NOTIFY structure [Buses], 61883/PBUS_RESET_NOTIFY, _BUS_RESET_NOTIFY
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	61883.h
apiname:
-	BUS_RESET_NOTIFY
product: Windows
targetos: Windows
req.typenames: BUS_RESET_NOTIFY, *PBUS_RESET_NOTIFY
---

# _BUS_RESET_NOTIFY structure


## -description


This structure is used to register or deregister the <a href="..\61883\nc-61883-pbus_reset_routine.md">PBUS_RESET_ROUTINE</a> callback. The request registers the caller to be notified when a reset of the 1394 bus occurs or cancels a previous registration. When the registered callback (bus reset) routine is called, the updated generation count and node address will be specified in parameter <b>BusResetInfo</b>. If a driver registers for bus-reset notification, it must cancel registration before the system unloads the driver.


## -syntax


````
typedef struct _BUS_RESET_NOTIFY {
  ULONG              Flags;
  PBUS_RESET_ROUTINE pfnNotify;
  PVOID              Context;
} BUS_RESET_NOTIFY, *PBUS_RESET_NOTIFY;
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20BUS_RESET_NOTIFY structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

