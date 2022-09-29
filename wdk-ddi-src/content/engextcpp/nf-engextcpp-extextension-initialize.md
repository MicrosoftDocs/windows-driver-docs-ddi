---
UID: NF:engextcpp.ExtExtension.Initialize
title: ExtExtension::Initialize (engextcpp.h)
description: The Initialize method is called by the engine to initialize an EngExtCpp extension library after loading it.
old-location: debugger\initialize.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtExtension::Initialize"]
ms.keywords: EngExtCpp_Ref_e6893e43-8573-4f07-baee-e9f4adcde156.xml, ExtExtension class [Windows Debugging],Initialize method, ExtExtension.Initialize, ExtExtension::Initialize, Initialize, Initialize method [Windows Debugging], Initialize method [Windows Debugging],ExtExtension class, debugger.initialize
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ExtExtension::Initialize
 - engextcpp/ExtExtension::Initialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtExtension::Initialize
---

# ExtExtension::Initialize


## -description

The <b>Initialize</b> method is called by the engine to initialize an EngExtCpp extension library after loading it.

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

The extension library version number should be set by this method.  This can be done by setting the members <b>m_ExtMajorVersion</b> and <b>m_ExtMinorVersion</b> of the base class <a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>.

The <b>ExtExtension</b> member <b>m_KnownStructs</b> should be set by this method to indicate to the engine which structures the extension library is capable of formatting for output.

If this method is defined in the extension library class <a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>, it can be used by the extension library to initialize any variables it requires.

There may or may not be a debugging session active when this function is called, so you should not assume that the extension can query session information.

## -see-also

<a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>



<a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>



<a href="/windows-hardware/drivers/ddi/portabledeviceclassextension/nf-portabledeviceclassextension-iportabledeviceclassextension-uninitialize">Uninitialize</a>

