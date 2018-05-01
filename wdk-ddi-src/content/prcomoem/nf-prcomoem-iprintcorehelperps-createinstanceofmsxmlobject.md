---
UID: NF:prcomoem.IPrintCoreHelperPS.CreateInstanceOfMSXMLObject
title: IPrintCoreHelperPS::CreateInstanceOfMSXMLObject
author: windows-driver-content
description: The IPrintCoreHelperPS::CreateInstanceOfMSXMLObject method creates an instance of an MSXML object.
old-location: print\iprintcorehelperps_createinstanceofmsxmlobject.htm
old-project: print
ms.assetid: 017f6e00-694b-4ada-86be-cf2be047fa88
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: CreateInstanceOfMSXMLObject, CreateInstanceOfMSXMLObject method [Print Devices], CreateInstanceOfMSXMLObject method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],CreateInstanceOfMSXMLObject method, IPrintCoreHelperPS.CreateInstanceOfMSXMLObject, IPrintCoreHelperPS::CreateInstanceOfMSXMLObject, prcomoem/IPrintCoreHelperPS::CreateInstanceOfMSXMLObject, print.iprintcorehelperps_createinstanceofmsxmlobject, print_unidrv-pscript_allplugins_c47c4793-f7d9-4688-a50c-3c39b6a9e15c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintCoreHelperPS.CreateInstanceOfMSXMLObject
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::CreateInstanceOfMSXMLObject


## -description


The <b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML object. 


## -parameters




### -param rclsid [in]

The CLSID that is associated with the data and code that will be used to create the object. 


### -param pUnkOuter [in]

A pointer to the aggregate object's <b>IUnknown</b> interface (the controlling <b>IUnknown</b>). This parameter must be <b>NULL</b>, which means that the object is not being created as part of an aggregate. 


### -param dwClsContext [in]

The context in which the code that manages the newly created object will run. The only valid values are <b>NULL</b> and CLSCTX_INPROC_SERVER, which is a value of the CLSCTX enumeration (described in the Microsoft Windows SDK documentation).


### -param riid [in]

A reference to the identifier of the interface that will be used to communicate with the object. 


### -param ppv [out]

A pointer to a memory address that receives the address of the interface that is requested in the <i>riid</i> parameter. If <b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> successfully returns, *<i>ppv</i> contains the address of the requested interface. If this method fails, *<i>ppv</i> contains <b>NULL</b>. 


## -returns



<b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> should return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
An instance of the specified object class was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CLASS_E_NOAGGREGATION</b></dt>
</dl>
</td>
<td width="60%">
The specified class cannot be created as part of an aggregate.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified class does not implement the requested interface, or the controlling <b>IUnknown</b> interface does not expose the requested interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>REGDB_E_CLASSNOTREG</b></dt>
</dl>
</td>
<td width="60%">
A specified class is not registered in the registration database. This value can also indicate that the type of server you requested in the CLSCTX enumeration type is not registered or the values for the server types in the registry are corrupt.

</td>
</tr>
</table>
 




## -remarks



The plug-in should not directly create an MSXML object by calling CoCreateInstance (described in the Windows SDK documentation). Instead, it should call Pscript to do so. The reason is that under certain conditions in which the printer driver might be used, such as with older operating system versions, the operating system does not need to register the required version of MSXML, which currently is version 6. In such situations, calling CoCreateInstance can fail. However, the core driver ensures that wherever the driver is present, the MSXML parser DLL is also present on the machine, making it possible to create an MSXML object when needed.



