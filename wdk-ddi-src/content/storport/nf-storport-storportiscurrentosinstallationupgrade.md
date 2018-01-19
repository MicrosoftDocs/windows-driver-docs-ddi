---
UID: NF:storport.StorPortIsCurrentOsInstallationUpgrade
title: StorPortIsCurrentOsInstallationUpgrade function
author: windows-driver-content
description: The StorPortIsCurrentOsInstallationUpgrade routine checks if the current installation of Windows is an upgrade from a previous version or not.
old-location: storage\storportiscurrentosinstallationupgrade.htm
old-project: storage
ms.assetid: 68D944D9-1A52-4FB0-B2D7-9680AB1EDABB
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortIsCurrentOsInstallationUpgrade
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortIsCurrentOsInstallationUpgrade
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: IRQL == PASSIVE_LEVEL
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortIsCurrentOsInstallationUpgrade function



## -description
The <b>StorPortIsCurrentOsInstallationUpgrade</b>  routine checks if the current installation of Windows is an upgrade from a previous version or not.



## -syntax

````
ULONG StorPortIsCurrentOsInstallationUpgrade(
  _In_  PVOID   HwDeviceExtension,
  _Out_ BOOLEAN *Upgraded
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Upgraded [out]

The value pointed to by <i>Upgraded</i> is set to <b>TRUE</b> if the current operating system installation was upgraded from a previous version. Otherwise, it is set to <b>FALSE</b>.


## -returns
The <b>StorPortIsCurrentOsInstallationUpgrade</b> routine returns one of these status codes:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>An upgrade status is returned in the value pointed to by the  <i>Upgraded</i> parameter.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer value  in <i>Upgraded</i> is NULL.
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>The current IRQL &gt; PASSIVE_LEVEL.

 


## -remarks
