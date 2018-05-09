---
UID: NF:storport.StorPortIsCurrentOsInstallationUpgrade
title: StorPortIsCurrentOsInstallationUpgrade function
author: windows-driver-content
description: The StorPortIsCurrentOsInstallationUpgrade routine checks if the current installation of Windows is an upgrade from a previous version or not.
old-location: storage\storportiscurrentosinstallationupgrade.htm
old-project: storage
ms.assetid: 68D944D9-1A52-4FB0-B2D7-9680AB1EDABB
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortIsCurrentOsInstallationUpgrade, StorPortIsCurrentOsInstallationUpgrade routine [Storage Devices], storage.storportiscurrentosinstallationupgrade, storport/StorPortIsCurrentOsInstallationUpgrade
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortIsCurrentOsInstallationUpgrade
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortIsCurrentOsInstallationUpgrade function


## -description


The <b>StorPortIsCurrentOsInstallationUpgrade</b>  routine checks if the current installation of Windows is an upgrade from a previous version or not.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Upgraded [out]

The value pointed to by <i>Upgraded</i> is set to <b>TRUE</b> if the current operating system installation was upgraded from a previous version. Otherwise, it is set to <b>FALSE</b>.


## -returns



The <b>StorPortIsCurrentOsInstallationUpgrade</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
An upgrade status is returned in the value pointed to by the  <i>Upgraded</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer value  in <i>Upgraded</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL &gt; PASSIVE_LEVEL.

</td>
</tr>
</table>
 



