---
UID: NC:bthddi.PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE
title: PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE
author: windows-driver-content
description: The IsBluetoothVersionAvailable function checks whether a given Bluetooth version is supported by the operating system.
old-location: bltooth\isbluetoothversionavailable.htm
old-project: bltooth
ms.assetid: 10662237-18b4-4f37-a704-985b2db0d689
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IsBluetoothVersionAvailable, IsBluetoothVersionAvailable callback function [Bluetooth Devices], PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE, bltooth.isbluetoothversionavailable, bth_funcs_34a25a87-fa07-46dc-aeaa-411009990c8b.xml, bthddi/IsBluetoothVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	bthddi.h
apiname:
-	IsBluetoothVersionAvailable
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE callback


## -description


The 
  <i>IsBluetoothVersionAvailable</i> function checks whether a given Bluetooth version is supported by the
  operating system.


## -prototype


````
PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE IsBluetoothVersionAvailable;

BOOLEAN IsBluetoothVersionAvailable(
  _In_ UCHAR MajorVersion,
  _In_ UCHAR MinorVersion
)
{ ... }
````


## -parameters




### -param MajorVersion [in]

This parameter specifies the major version number of Bluetooth that is requested.


### -param MinorVersion [in]

This parameter specifies the minor version number of Bluetooth that is requested.


## -returns



<i>IsBluetoothVersionAvailable</i> returns <b>TRUE</b> if the Bluetooth version that the operating system
     provides is greater than or equal to the Bluetooth version number that is being requested.




## -remarks



Bluetooth profile drivers should call this function before performing any operations that are not
    supported in all Bluetooth versions.



