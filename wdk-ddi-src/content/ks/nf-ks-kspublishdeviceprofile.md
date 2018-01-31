---
UID: NF:ks.KsPublishDeviceProfile
title: KsPublishDeviceProfile function
author: windows-driver-content
description: The KsPublishDeviceProfile API is called to publish device profile information.
old-location: stream\kspublishdeviceprofile.htm
old-project: stream
ms.assetid: 944A593D-D623-400C-80F9-6DCD973681C9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPublishDeviceProfile, stream.kspublishdeviceprofile, KsPublishDeviceProfile function [Streaming Media Devices], ks/KsPublishDeviceProfile
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ks.lib
-	ks.dll
apiname:
-	KsPublishDeviceProfile
product: Windows
targetos: Windows
req.typenames: 
---

# KsPublishDeviceProfile function


## -description


The <b>KsPublishDeviceProfile</b> API is called to publish device profile information.


## -syntax


````
 __drv_maxIRQL(PASSIVE_LEVEL) KSDDKAPI NTSTATUS NTAPI KsPublishDeviceProfile(
  _In_ PKSFILTERFACTORY       FilterFactory,
  _In_ PKSDEVICE_PROFILE_INFO Profile
);
````


## -parameters




#### - FilterFactory [in]

This is the same <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> used in the <a href="..\ks\nf-ks-ksinitializedeviceprofile.md">KsInitializeDeviceProfile</a> API.


#### - Profile [in]

This is a camera profile of type <a href="..\ksmedia\ns-ksmedia-_ksdevice_profile_info.md">KSDEVICE_PROFILE_INFO</a>.


## -returns


Camera profile information will only be associated with the <b>KSCATEGORY_VIDEO_CAMERA</b> interface category.  Any filter factory created without this interface category and attempting to register a camera profile will result in this API returning a <b>STATUS_INVALID_PARAMETER</b>.



## -remarks


This API will be called repeatedly for each profile the camera driver supports.  Each call may have different set of concurrency and data range information.  The <b>ProfileId</b> field of the <b>KSCAMERA_PROFILE_INFO</b> must be unique.  If the same <b>ProfileId</b> is used and the content of the profile information is different, the subsequent call will overwrite the earlier profile information.


