---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_SET_PROPERTY
title: UFX_PROPRIETARY_CHARGER_SET_PROPERTY
description: The filter driver's implementation to set a configurable property on the charger.
old-location: buses\ufx_proprietary_charger_set_property.htm
tech.root: usbref
ms.assetid: 504878FA-3234-4BE7-95D9-6CCE08DB4D8A
ms.date: 05/07/2018
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_SET_PROPERTY, PFN_UFX_PROPRIETARY_CHARGER_SET_PROPERTY callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_SET_PROPERTY, UFX_PROPRIETARY_CHARGER_SET_PROPERTY callback, UfxProprietaryChargerSetProperty, UfxProprietaryChargerSetProperty callback function [Buses], buses.ufx_proprietary_charger_set_property, ufxproprietarycharger/UfxProprietaryChargerSetProperty
ms.topic: callback
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	ufxproprietarycharger.h
api_name:
-	PFN_UFX_PROPRIETARY_CHARGER_SET_PROPERTY
product:
- Windows
targetos: Windows
req.typenames: 
---

# UFX_PROPRIETARY_CHARGER_SET_PROPERTY callback function


## -description


The filter driver's implementation to set a configurable property on the charger.


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


### -param Property [in]

    A pointer to a <b>CONFIGURABLE_CHARGER_PROPERTY_HEADER</b> structure (defined in charging.h) that describes the configurable charger property to set.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.

In this callback function, the driver sets the specified property value. For example, after the detection of a HVDCP charger, the driver sets the output voltages to the specified value. 




## -see-also




<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>
 

 

