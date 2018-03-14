---
UID: NF:wiamdef.CWiaLogProc.CWiaLogProc
title: CWiaLogProc::CWiaLogProc method
author: windows-driver-content
description: The CWiaLogProc constructor is called when the function or method being logged is entered.
old-location: image\cwialogproc_cwialogproc.htm
old-project: image
ms.assetid: FB963A5D-ACB2-4720-95D1-0CA1661A99C9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: CWiaLogProc, CWiaLogProc interface [Imaging Devices], CWiaLogProc method, CWiaLogProc method [Imaging Devices], CWiaLogProc method [Imaging Devices], CWiaLogProc interface, CWiaLogProc,CWiaLogProc.CWiaLogProc, CWiaLogProc::CWiaLogProc, image.cwialogproc_cwialogproc, wiamdef/CWiaLogProc::CWiaLogProc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamdef.h
req.include-header: Wiamdef.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wiamdef.h
api_name:
-	CWiaLogProc.CWiaLogProc
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# CWiaLogProc::CWiaLogProc method


## -description


The <a href="https://msdn.microsoft.com/5DD3EC13-5DDD-4640-A841-00576F74429A">CWiaLogProc</a> constructor is called when the function or method being logged is entered.


## -syntax


````
void CWiaLogProc(
   IWiaLog     *pIWiaLog,
   INT         ResourceID,
   INT         DetailLevel,
   _In_z_ CHAR *pszMsg
);
````


## -parameters




### -param pIWiaLog




### -param ResourceID

Defines the <b>INT</b> parameter <i>ResourceID</i>.


### -param DetailLevel

Defines the <b>INT</b> parameter <i>DetailLevel</i>.


### -param pszMsg






#### - *pIWiaLog

Defines the <b>IWiaLog</b> parameter <i>*pIWiaLog</i>.


#### - *pszMsg

Defines the <b>CHAR</b> parameter <i>*pszMsg</i>.


## -returns



This method does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt844724">CWiaLogProc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiaLogProc::CWiaLogProc method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

