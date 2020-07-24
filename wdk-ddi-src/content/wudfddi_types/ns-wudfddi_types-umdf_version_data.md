---
UID: NS:wudfddi_types.UMDF_VERSION_DATA
title: UMDF_VERSION_DATA (wudfddi_types.h)
description: The UMDF_VERSION_DATA structure describes a version of the framework.
old-location: wdf\umdf_version_data.htm
tech.root: wdf
ms.assetid: b83a786d-0b17-4129-bdd4-86942ad9d3ec
ms.date: 02/26/2018
keywords: ["UMDF_VERSION_DATA structure"]
ms.keywords: "*PUMDF_VERSION_DATA, PUMDF_VERSION_DATA, PUMDF_VERSION_DATA structure pointer, UMDF_VERSION_DATA, UMDF_VERSION_DATA structure, umdf.umdf_version_data, umdfstructs_b4fe6241-b095-437b-a3f8-e1cf395da8ee.xml, wdf.umdf_version_data, wudfddi_types/PUMDF_VERSION_DATA, wudfddi_types/UMDF_VERSION_DATA"
f1_keywords:
 - "wudfddi_types/UMDF_VERSION_DATA"
 - "UMDF_VERSION_DATA"
req.header: wudfddi_types.h
req.include-header: Wudfddi_types.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_types.h
api_name:
- UMDF_VERSION_DATA
targetos: Windows
req.typenames: UMDF_VERSION_DATA, *PUMDF_VERSION_DATA
---

# UMDF_VERSION_DATA structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UMDF_VERSION_DATA</b> structure describes a version of the framework.


## -struct-fields




### -field MajorNumber

A number that specifies the major version of the framework. 


### -field MinorNumber

A number that specifies the minor version of the framework. 


### -field ServiceNumber

A number that specifies the service of the framework. 


## -remarks



A UMDF driver supplies a pointer to a <b>UMDF_VERSION_DATA</b> structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-isversionavailable">IWDFDriver::IsVersionAvailable</a> method to describe the minimum version of the framework that the driver supports.

<div class="alert"><b>Note</b>  <b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.</div>
<div> </div>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-umdf_version_data">Microsoft_WDF_UMDF_Version</a> is a global variable of type  <b>UMDF_VERSION_DATA</b> that specifies the major version, minor version, and service number for the current release of the framework.
      

For example, in Windows 8, Wudfddi.h specifies: <div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UMDF_VERSION_DATA Microsoft_WDF_UMDF_Version = {1, 11,  0}</pre>
</td>
</tr>
</table></span></div>


When you compile a driver using Wudfddi.h, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-umdf_version_data">Microsoft_WDF_UMDF_Version</a> is included in the driver binary and exported using <a href="https://docs.microsoft.com/cpp/build/exporting-from-a-dll-using-declspec-dllexport">__declspec(dllexport)</a>.

 When the system loads your driver, the host process (WUDFHost.exe) verifies  that the driver's major version matches the framework's major version and that the driver's minor version is less than or equal to the framework's minor version.

  The driver does not need to take any action to provide this version number to the framework, other than building with Wudfddi.h.

End of support:
 Unavailable in UMDF 2.0 and later.

Minimum UMDF version:
 1.0

Header:
 Wudfddi.h (include Wudfddi.h) 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-isversionavailable">IWDFDriver::IsVersionAvailable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-umdf_version_data">Microsoft_WDF_UMDF_Version</a>
 

 

