---
UID: NF:wiamicro.MicroEntry
title: MicroEntry function
author: windows-driver-content
description: The MicroEntry function responds to commands sent by the WIA Flatbed driver.
old-location: image\microentry.htm
old-project: image
ms.assetid: 3e0c51af-ceb9-4c06-ab6a-ccc468997fdd
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , E, M, MicroDrv_04aa15b3-5e4d-453d-b41a-a4de3c1228f7.xml, MicroEntry, MicroEntry function [Imaging Devices], c, i, image.microentry, n, o, r, t, wiamicro/MicroEntry, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamicro.h
apiname:
-	MicroEntry
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# MicroEntry function


## -description


The<b> MicroEntry </b>function responds to commands sent by the WIA Flatbed driver. 


## -syntax


````
WIAMICRO_API HRESULT MicroEntry(
          LONG lCommand,
  _Inout_ PVAL pValue
);
````


## -parameters




### -param lCommand

Specifies a command issued to the microdriver by the WIA Flatbed driver. 


### -param pValue [in, out]

Points to a <a href="..\wiamicro\ns-wiamicro-val.md">VAL</a> structure that is used to pass information between the WIA Flatbed driver and the microdriver.


## -returns



If the function succeeds, it returns S_OK. If a passed command is not supported,  the function returns E_NOTIMPL. For any error, error information must be put in the <b>lVal</b> member of the VAL structure pointed to by <i>pValue</i>.




## -remarks



This function performs many different tasks, depending on the command passed in the <i>lCommand</i> parameter. See the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552714">WIA Microdriver Commands</a> reference section for a list of these commands.

Two structures are passed to the function. A <a href="..\wiamicro\ns-wiamicro-val.md">VAL</a> structure is passed in the <i>pValue</i> pointer, and the <b>pScanInfo</b> member of the VAL structure points to a <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure. The VAL structure is used to pass information between the WIA Flatbed Driver and the microdriver. The SCANINFO structure is used to store and communicate parameters of a scan data acquisition. Many of the commands passed to this function set values in the SCANINFO structure.




## -see-also

<a href="..\wiamicro\ns-wiamicro-val.md">VAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552722">WIA Microdriver Structures</a>



<a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552714">WIA Microdriver Commands</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20MicroEntry function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

