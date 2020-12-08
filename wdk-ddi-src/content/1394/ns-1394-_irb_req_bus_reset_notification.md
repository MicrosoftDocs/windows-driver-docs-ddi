---
UID: NS:1394._IRB_REQ_BUS_RESET_NOTIFICATION
title: _IRB_REQ_BUS_RESET_NOTIFICATION (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to carry out a bus reset notification request.
old-location: ieee\irb_req_bus_reset_notification.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IRB_REQ_BUS_RESET_NOTIFICATION structure"]
ms.keywords: 1394/IRB_REQ_BUS_RESET_NOTIFICATION, IEEE.irb_req_bus_reset_notification, IRB_REQ_BUS_RESET_NOTIFICATION, IRB_REQ_BUS_RESET_NOTIFICATION structure [Buses], _IRB_REQ_BUS_RESET_NOTIFICATION
req.header: 1394.h
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
targetos: Windows
req.typenames: IRB_REQ_BUS_RESET_NOTIFICATION
f1_keywords:
 - _IRB_REQ_BUS_RESET_NOTIFICATION
 - 1394/_IRB_REQ_BUS_RESET_NOTIFICATION
 - IRB_REQ_BUS_RESET_NOTIFICATION
 - 1394/IRB_REQ_BUS_RESET_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_BUS_RESET_NOTIFICATION
---

# _IRB_REQ_BUS_RESET_NOTIFICATION structure


## -description

This structure contains the fields necessary for the 1394 bus driver to carry out a bus reset notification request. 

This is the suggested method for a client driver on top of the 1394 bus driver to get notified about 1394 bus resets. The client registers by using this IRB in its START_DEVICE routine, and de-registers using the same IRB, but with different flags, in its REMOVE routine. 

This notification is only issued if after the bus reset, the target device is still present on the bus. This way the caller does not have to verify that the target device is on the bus.

## -struct-fields

### -field fulFlags

Specifies whether a callback should be registered or deactivated. Use REGISTER_NOTIFICATION_ROUTINE to register <b>ResetRoutine</b> as the callback. Use DEREGISTER_NOTIFICATION_ROUTINE to deactivate any previously registered callback.

<div class="alert"><b>Note</b>  In Windows 7 and later, set the EXTENDED_NOTIFICATION_ROUTINE flag  to register for extended bus reset notifications supported by the new IEEE 1394 bus driver. This notification returns information about the current generation of the bus, such as the generation count and node ids, to 1394 client drivers in the context of the bus reset notification.</div>
<div> </div>

### -field ResetRoutine

Points to the notification routine for bus resets. The notification routine parameters follow this prototype:


```
void BusResetNotificationRoutine(IN PVOID Context);
 
```


### -field ResetContext

Specifies the argument to be passed to the notification routine.

When the EXTENDED_NOTIFICATION_ROUTINE flag is specified, <b>ResetContext</b> points to a <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_bus_reset_data">BUS_RESET_DATA</a> structure.
