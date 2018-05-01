---
UID: NS:ucmtypes._UCM_PD_REQUEST_DATA_OBJECT
title: "_UCM_PD_REQUEST_DATA_OBJECT"
author: windows-driver-content
description: Describes a Request Data Object (RDO). For information about these members, see the Power Delivery specification.
old-location: buses\ucm_pd_request_data_object.htm
old-project: usbref
ms.assetid: 2F5CC46B-3BFC-4C69-A9C8-C4BC4864E84B
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUCM_PD_REQUEST_DATA_OBJECT, PUCM_PD_REQUEST_DATA_OBJECT, PUCM_PD_REQUEST_DATA_OBJECT union pointer [Buses], UCM_PD_REQUEST_DATA_OBJECT, UCM_PD_REQUEST_DATA_OBJECT union [Buses], _UCM_PD_REQUEST_DATA_OBJECT, buses.ucm_pd_request_data_object, ucmtypes/PUCM_PD_REQUEST_DATA_OBJECT, ucmtypes/UCM_PD_REQUEST_DATA_OBJECT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	ucmtypes.h
api_name:
-	UCM_PD_REQUEST_DATA_OBJECT
product: Windows
targetos: Windows
req.typenames: UCM_PD_REQUEST_DATA_OBJECT, *PUCM_PD_REQUEST_DATA_OBJECT
---

# _UCM_PD_REQUEST_DATA_OBJECT structure


## -description


Describes a Request Data Object (RDO). For information about these members, see the <a href="http://www.usb.org/developers/docs/usb20_docs/">Power Delivery specification</a>.


## -struct-fields




### -field Ul

Size of the structure.


### -field Common


### -field Common.Reserved1

Reserved.


### -field Common.ObjectPosition

Object position.


### -field Common.Reserved2

Reserved.


### -field FixedAndVariableRdo


### -field FixedAndVariableRdo.MaximumOperatingCurrentIn10mA

Maximum current in 10 mA units.


### -field FixedAndVariableRdo.OperatingCurrentIn10mA

Operating current in 10mA units.


### -field FixedAndVariableRdo.Reserved1

Reserved.


### -field FixedAndVariableRdo.NoUsbSuspend

Indicates support for USB suspend.




### -field FixedAndVariableRdo.UsbCommunicationCapable

USB communication capable. 


### -field FixedAndVariableRdo.CapabilityMismatch

Capability Mismatch 


### -field FixedAndVariableRdo.GiveBackFlag

GiveBack Flag.


### -field FixedAndVariableRdo.ObjectPosition

Object Position.


### -field FixedAndVariableRdo.Reserved2

Reserved for future use.


### -field BatteryRdo


### -field BatteryRdo.MaximumOperatingPowerIn250mW

Maximum Operating Power in 250mW units. 


### -field BatteryRdo.OperatingPowerIn250mW

Operating Power in 250mW units.


### -field BatteryRdo.Reserved1

Reserved for future use.


### -field BatteryRdo.NoUsbSuspend

 USB Suspend. 


### -field BatteryRdo.UsbCommunicationCapable

USB Communications Capable.


### -field BatteryRdo.CapabilityMismatch

Capability Mismatch. 


### -field BatteryRdo.GiveBackFlag

GiveBack Flag. 


### -field BatteryRdo.ObjectPosition

Object Position.


### -field BatteryRdo.Reserved2

Reserved.

