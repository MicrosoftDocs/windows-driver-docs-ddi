---
UID: NF:engextcpp.ExtExtension.Initialize
title: ExtExtension::Initialize method
author: windows-driver-content
description: The Initialize method is called by the engine to initialize an EngExtCpp extension library after loading it.
old-location: debugger\initialize.htm
old-project: debugger
ms.assetid: 0de57ce8-cb09-40b0-8db0-ed4e910c6d53
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_e6893e43-8573-4f07-baee-e9f4adcde156.xml, ExtExtension, ExtExtension class [Windows Debugging], Initialize method, ExtExtension::Initialize, Initialize method [Windows Debugging], Initialize method [Windows Debugging], ExtExtension class, Initialize,ExtExtension.Initialize, debugger.initialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtExtension.Initialize
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::Initialize method


## -description


The <b>Initialize</b> method is called by the engine to initialize an EngExtCpp extension library after loading it.


## -syntax


````
virtual HRESULT Initialize();
````


## -parameters






## -returns



This method can return one of these values.

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
The extension library was successfully initialized.

</td>
</tr>
</table>
 




## -remarks



The extension library version number should be set by this method.  This can be done by setting the members <b>m_ExtMajorVersion</b> and <b>m_ExtMinorVersion</b> of the base class <a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>.

The <b>ExtExtension</b> member <b>m_KnownStructs</b> should be set by this method to indicate to the engine which structures the extension library is capable of formatting for output.

If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used by the extension library to initialize any variables it requires.

There may or may not be a debugging session active when this function is called, so you should not assume that the extension can query session information.




## -see-also

<a href="..\engextcpp\nf-engextcpp-extextension-uninitialize.md">Uninitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.Initialize method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

