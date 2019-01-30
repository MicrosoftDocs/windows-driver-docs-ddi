---
UID: NF:ks.KsPersistDeviceProfile
title: KsPersistDeviceProfile function (ks.h)
description: The KsPersistDeviceProfile API commits the profile information to the persistent store.
old-location: stream\kspersistdeviceprofile.htm
tech.root: stream
ms.assetid: 4EC3E99B-C73C-4EAC-9EBD-BB45ABFCE8EC
ms.date: 04/23/2018
ms.keywords: KsPersistDeviceProfile, KsPersistDeviceProfile function [Streaming Media Devices], ks/KsPersistDeviceProfile, stream.kspersistdeviceprofile
ms.topic: function
req.header: ks.h
req.include-header: Ksmedia.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ks.lib
-	ks.dll
api_name:
-	KsPersistDeviceProfile
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPersistDeviceProfile function


## -description


The <b>KsPersistDeviceProfile</b> API commits the profile information to the persistent store.


## -parameters




### -param FilterFactory [in]

This is the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> that was used to initialize the profile store in <a href="https://msdn.microsoft.com/library/windows/hardware/dn917797">KsInitializeDeviceProfile</a>.


## -returns



If <b>KsPersistDeviceProfile</b> is called without first initializing the profile store with <b>KsInitializeDeviceProfile</b> the call to <b>KsPersistDeviceProfile</b> will fail with <b>STATUS_INVALID_DEVICE_REQUEST</b>.
Furthermore, this API may also fail with <b>STATUS_INSUFFICIENT_RESOURCE</b> if the page pool is exhausted when profile information is being persisted.



