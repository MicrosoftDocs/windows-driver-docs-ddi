---
UID: NF:printerextension.IPrinterExtensionContextCollection.GetAt
title: IPrinterExtensionContextCollection::GetAt (printerextension.h)
description: Gets a pointer to an IPrinterExtensionContext object.
old-location: print\iprinterextensioncontextcollection_getat.htm
tech.root: print
ms.assetid: 5E3DC6C7-E370-4120-81B7-2093812AD009
ms.date: 04/20/2018
ms.keywords: GetAt, GetAt method [Print Devices], GetAt method [Print Devices],IPrinterExtensionContextCollection interface, IPrinterExtensionContextCollection interface [Print Devices],GetAt method, IPrinterExtensionContextCollection.GetAt, IPrinterExtensionContextCollection::GetAt, get_GetAt, print.iprinterextensioncontextcollection_getat, printerextension/IPrinterExtensionContextCollection::GetAt
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterExtensionContextCollection.GetAt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionContextCollection::GetAt


## -description


Gets a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a> object.


## -parameters




### -param ulIndex [in]

The index of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a> object within the collection.


### -param ppContext [out, retval]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a> interface.


## -returns



This method returns an <b>HRESULT</b> value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh846191">IPrinterExtensionContextCollection</a>
 

 

