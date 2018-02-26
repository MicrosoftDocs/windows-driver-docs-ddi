---
UID: NF:sti.IStillImageW.UnregisterLaunchApplication
title: IStillImageW::UnregisterLaunchApplication method
author: windows-driver-content
description: The IStillImage::UnregisterLaunchApplication method removes an application from the still image event monitor's list of push-model aware applications.
old-location: image\istillimage_unregisterlaunchapplication.htm
old-project: image
ms.assetid: cf57265a-d343-4e49-9635-6a4663c9a3a5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, A, I, IStillImageW, IStillImageW interface [Imaging Devices], UnregisterLaunchApplication method, IStillImageW::UnregisterLaunchApplication, L, S, U, UnregisterLaunchApplication method [Imaging Devices], UnregisterLaunchApplication method [Imaging Devices], IStillImageW interface, UnregisterLaunchApplication,IStillImageW.UnregisterLaunchApplication, W, a, c, e, g, h, i, image.istillimage_unregisterlaunchapplication, l, m, n, o, p, r, s, sti/IStillImageW::UnregisterLaunchApplication, stifnc_7e477efa-efa3-445d-bd68-a23f87cee5de.xml, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
req.target-type: Desktop
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStillImageW.UnregisterLaunchApplication
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::UnregisterLaunchApplication method


## -description


The <b>IStillImage::UnregisterLaunchApplication</b> method removes an application from the still image event monitor's list of push-model aware applications.


## -syntax


````
HRESULT UnregisterLaunchApplication(
  [in] LPWSTR pwszAppName
);
````


## -parameters




### -param pwszAppName [in]

Caller-supplied pointer to the application's "short name".


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::UnRegisterLaunchApplication</b> method should be called as part of the process of uninstalling a push-model aware application. The method can be uninstalled either by the application itself or by other uninstalling software.

Before calling <b>IStillImage::UnRegisterLaunchApplication</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also

<a href="..\sti\nn-sti-istillimagew.md">IStillImageW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543798">IStillImage::RegisterLaunchApplication</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImageW::UnregisterLaunchApplication method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

