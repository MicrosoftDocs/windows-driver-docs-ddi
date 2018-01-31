---
UID: NF:wdfinstaller.WdfPostDeviceInstall
title: WdfPostDeviceInstall function
author: windows-driver-content
description: The co-installer's WdfPostDeviceInstall function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has created the driver's kernel-mode service.
old-location: wdf\wdfpostdeviceinstall.htm
old-project: wdf
ms.assetid: 78942ef8-ecf9-481f-af60-2f1266a9e73f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFCoinstallerRef_6a05795f-99bb-4f4d-975f-8d2de85adff0.xml, kmdf.wdfpostdeviceinstall, WdfPostDeviceInstall function, PFN_WDFPOSTDEVICEINSTALL, wdfinstaller/WdfPostDeviceInstall, wdf.wdfpostdeviceinstall, WdfPostDeviceInstall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	N/A
-	N/A.dll
apiname:
-	WdfPostDeviceInstall
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WdfPostDeviceInstall function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The co-installer's <b>WdfPostDeviceInstall</b> function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has created the driver's kernel-mode service. 


## -syntax


````
ULONG WdfPostDeviceInstall(
  _In_     LPCWSTR InfPath,
  _In_opt_ LPCWSTR InfSectionName
);
````


## -parameters




#### - InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <b>GetCurrentDirectory</b>, which is described in the Microsoft Windows SDK.


#### - InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


## -returns


<b>WdfPostDeviceInstall</b> returns ERROR_SUCCESS if the operation succeeds. Otherwise, the function returns one of the additional ERROR_<i>XXX</i> values that are defined in <i>Winerror.h</i>.



## -remarks


The installer for the framework-based drivers of a non-PnP device must call <b>WdfPostDeviceInstall</b> after the installer calls <b>CreateService</b>.

To obtain the address of the co-installer's <b>WdfPostDeviceInstall</b> function, the installer must call <b>GetProcAddress</b> after the installer has called <b>LoadLibrary</b> to load the co-installer.

For more information about the <b>WdfPostDeviceInstall</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <b>CreateService</b>, <b>GetProcAddress</b>, and <b>LoadLibrary</b>, see the Microsoft Windows SDK documentation.



## -see-also

<a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstall.md">WdfPreDeviceInstall</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPostDeviceInstall function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

