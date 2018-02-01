---
UID: NF:prcomoem.IPrintCoreHelper.CreateInstanceOfMSXMLObject
title: IPrintCoreHelper::CreateInstanceOfMSXMLObject method
author: windows-driver-content
description: The IPrintCoreHelper::CreateInstanceOfMSXMLObject method creates an instance of an MSXML 6.0 object by using the correct MSXML DLL.
old-location: print\iprintcorehelper_createinstanceofmsxmlobject.htm
old-project: print
ms.assetid: d4b91262-f349-4824-bab0-5e3725a81cb3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintCoreHelper, CreateInstanceOfMSXMLObject, print.iprintcorehelper_createinstanceofmsxmlobject, print_unidrv-pscript_allplugins_2768e9fd-1f73-400c-8e16-e1376a0e8633.xml, IPrintCoreHelper::CreateInstanceOfMSXMLObject, CreateInstanceOfMSXMLObject method [Print Devices], IPrintCoreHelper interface, prcomoem/IPrintCoreHelper::CreateInstanceOfMSXMLObject, CreateInstanceOfMSXMLObject method [Print Devices], IPrintCoreHelper interface [Print Devices], CreateInstanceOfMSXMLObject method
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintCoreHelper.CreateInstanceOfMSXMLObject
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelper::CreateInstanceOfMSXMLObject method


## -description


The <b>IPrintCoreHelper::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML 6.0 object by using the correct MSXML DLL. 


## -syntax


````
HRESULT CreateInstanceOfMSXMLObject(
  [in]  REFCLSID  rclsid,
  [in]  LPUNKNOWN pUnkOuter,
  [in]  DWORD     dwClsContext,
  [in]  REFIID    riid,
  [out] LPVOID    *ppv
);
````


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

A pointer to a variable that receives the address of the interface that is requested in the <i>riid</i> parameter. If <b>IPrintCoreHelper::CreateInstanceOfMSXMLObject</b> successfully returns, *<i>ppv</i> contains the address of the requested interface. If this method fails, *<i>ppv</i> contains <b>NULL</b>. 


## -returns


<b>IPrintCoreHelper::CreateInstanceOfMSXMLObject</b> should return one of the following values.
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


<b>IPrintCoreHelper::CreateInstanceOfMSXMLObject</b> enables a plug-in to use MSXML objects safely even when it runs on down-level client machines (that is, client machines that run Windows Server 2003, Windows XP, or Windows 2000). 

The parameters in this method map directly to those of the <b>CoCreateInstance</b> function (which is described in the Windows SDK documentation). Note that installing a Windows Vista driver on a machine that runs a previous version of Windows does not cause MSXML 6.0 to be installed. The actual DLL is included with the driver-dependent DLLs and is loaded from the driver directory. It is not registered on the system. Plug-ins that use this method should create only MSXML objects.


