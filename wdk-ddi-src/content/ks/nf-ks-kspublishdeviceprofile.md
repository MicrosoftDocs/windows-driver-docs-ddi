---
UID: NF:ks.KsPublishDeviceProfile
title: KsPublishDeviceProfile function (ks.h)
description: The KsPublishDeviceProfile API is called to publish device profile information.
old-location: stream\kspublishdeviceprofile.htm
tech.root: stream
ms.assetid: 944A593D-D623-400C-80F9-6DCD973681C9
ms.date: 04/23/2018
keywords: ["KsPublishDeviceProfile function"]
ms.keywords: KsPublishDeviceProfile, KsPublishDeviceProfile function [Streaming Media Devices], ks/KsPublishDeviceProfile, stream.kspublishdeviceprofile
f1_keywords:
 - "ks/KsPublishDeviceProfile"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ks.lib
- ks.dll
api_name:
- KsPublishDeviceProfile
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPublishDeviceProfile function


## -description


The <b>KsPublishDeviceProfile</b> API is called to publish device profile information.


## -parameters




### -param FilterFactory [in]

This is the same <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksinitializedeviceprofile">KsInitializeDeviceProfile</a> API.


### -param Profile [in]

This is a camera profile of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ksdevice_profile_info">KSDEVICE_PROFILE_INFO</a>.


## -returns



Camera profile information will only be associated with the <b>KSCATEGORY_VIDEO_CAMERA</b> interface category.  Any filter factory created without this interface category and attempting to register a camera profile will result in this API returning a <b>STATUS_INVALID_PARAMETER</b>.




## -remarks



This API will be called repeatedly for each profile the camera driver supports.  Each call may have different set of concurrency and data range information.  The <b>ProfileId</b> field of the <b>KSCAMERA_PROFILE_INFO</b> must be unique.  If the same <b>ProfileId</b> is used and the content of the profile information is different, the subsequent call will overwrite the earlier profile information.



