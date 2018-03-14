---
UID: NA:wiautil
ms.assetid: 772a15b8-8c34-3cf7-8c3b-dca823285720
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wiautil.h header



This header is used by Imaging devices. For more information, see
- [Imaging devices](../_image/index.md)

Wiautil.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [wiauDbgDump function](nf-wiautil-wiaudbgdump.md) | The wiauDbgDump function logs a message containing one or more data values. |
| [wiauDbgError function](nf-wiautil-wiaudbgerror.md) | The wiauDbgError function logs an error message. |
| [wiauDbgErrorHr function](nf-wiautil-wiaudbgerrorhr.md) | The wiauDbgErrorHr function logs a message containing an HRESULT and its error message string. |
| [wiauDbgFlags function](nf-wiautil-wiaudbgflags.md) | The wiauDbgFlags function determines whether a particular debugging flag is set. |
| [wiauDbgHelper2 function](nf-wiautil-wiaudbghelper2.md) | The wiauDbgHelper2 function writes a message to a log file, or debugger, or both. |
| [wiauDbgLegacyError function](nf-wiautil-wiaudbglegacyerror.md) | The wiauDbgLegacyError function logs an error message. |
| [wiauDbgLegacyError2 function](nf-wiautil-wiaudbglegacyerror2.md) | The wiauDbgLegacyError2 function logs an error message. |
| [wiauDbgLegacyHresult2 function](nf-wiautil-wiaudbglegacyhresult2.md) | The wiauDbgLegacyHresult2 function logs a default message containing an HRESULT. |
| [wiauDbgLegacyTrace function](nf-wiautil-wiaudbglegacytrace.md) | The wiauDbgLegacyTrace function logs a trace message. |
| [wiauDbgLegacyTrace2 function](nf-wiautil-wiaudbglegacytrace2.md) | The wiauDbgLegacyTrace2 function logs a trace message. |
| [wiauDbgLegacyWarning function](nf-wiautil-wiaudbglegacywarning.md) | The wiauDbgLegacyWarning function logs a warning message. |
| [wiauDbgTrace function](nf-wiautil-wiaudbgtrace.md) | The wiauDbgTrace function logs a trace message. |
| [wiauDbgWarning function](nf-wiautil-wiaudbgwarning.md) | The wiauDbgWarning function logs a warning message. |
| [wiauGetDrvItemContext function](nf-wiautil-wiaugetdrvitemcontext.md) | The wiauGetDrvItemContext function gets the driver item context, and optionally, the driver item. |
| [wiauGetResourceString function](nf-wiautil-wiaugetresourcestring.md) | The wiauGetResourceString function gets a resource string, storing it as a BSTR. |
| [wiauGetValidFormats function](nf-wiautil-wiaugetvalidformats.md) | The wiauGetValidFormats function calls the IWiaMiniDrv |
| [wiauPropInPropSpec function](nf-wiautil-wiaupropinpropspec.md) | The wiauPropInPropSpec function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found. |
| [wiauPropsInPropSpec function](nf-wiautil-wiaupropsinpropspec.md) | The wiauPropsInPropSpec function determines whether any of a list of property specification IDs is contained within an array of such values. |
| [wiauRegGetDwordA function](nf-wiautil-wiaureggetdworda.md) | The wiauRegGetDword function gets a DWORD value from the DeviceData section of the registry. |
| [wiauRegGetDwordW function](nf-wiautil-wiaureggetdwordw.md) | The wiauRegGetDword function gets a DWORD value from the DeviceData section of the registry. |
| [wiauRegGetStrA function](nf-wiautil-wiaureggetstra.md) | The wiauRegGetStr function gets a string value from the DeviceData section of the registry. |
| [wiauRegGetStrW function](nf-wiautil-wiaureggetstrw.md) | The wiauRegGetStr function gets a string value from the DeviceData section of the registry. |
| [wiauRegOpenDataA function](nf-wiautil-wiauregopendataa.md) | The wiauRegOpenData function opens the DeviceData registry key. |
| [wiauRegOpenDataW function](nf-wiautil-wiauregopendataw.md) | The wiauRegOpenData function opens the DeviceData registry key. |
| [wiauSetImageItemSize function](nf-wiautil-wiausetimageitemsize.md) | The wiauSetImageItemSize function calculates the size and width, in bytes, for an image, based on the current WIA_IPA_FORMAT setting (described in the Microsoft Windows SDK documentation), and writes the new values to the appropriate properties. |
| [wiauStrC2C function](nf-wiautil-wiaustrc2c.md) | The wiauStrC2C function copies an ANSI character string to another ANSI character string. |
| [wiauStrC2W function](nf-wiautil-wiaustrc2w.md) | The wiauStrC2W function converts an ANSI character string to a Unicode string. |
| [wiauStrW2C function](nf-wiautil-wiaustrw2c.md) | The wiauStrW2C function converts a Unicode string to an ANSI character string. |
| [wiauStrW2W function](nf-wiautil-wiaustrw2w.md) | The wiauStrW2W function copies a Unicode string to another Unicode string. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_BMP_IMAGE_INFO structure](ns-wiautil-_bmp_image_info.md) | The BMP_IMAGE_INFO structure contains information about a BMP image. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [SKIP_AMOUNT enumeration](ne-wiautil-skip_amount.md) | The SKIP_AMOUNT enumeration is used to indicate whether the file and informational headers of an image should be skipped over. |

## Classes

| Title   | Description   |
| ---- |:---- |
| [CWiauDbgFn class](nl-wiautil-cwiaudbgfn.md) | The CWiauDbgFn class is a helper class that is used for tracing function or method entry and exit points. |
| [CWiauFormatConverter class](nl-wiautil-cwiauformatconverter.md) | The CWiauFormatConverter class is a helper class for converting images to BMP format. |
| [CWiauPropertyList class](nl-wiautil-cwiaupropertylist.md) | The CWiauPropertyList class can be used to create and maintain a list of properties for a device. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [WIAS_ASSERT macro](nf-wiautil-wias_assert.md) | The WIAS_ASSERT macro writes a diagnostic message to the Wiatrace.log file. |
| [WIAS_ERROR macro](nf-wiautil-wias_error.md) | The WIAS_ERROR macro writes a diagnostic message to the Wiatrace.log file. |
| [WIAS_HRESULT macro](nf-wiautil-wias_hresult.md) | The WIAS_HRESULT macro writes a diagnostic message to the Wiatrace.log file. |
| [WIAS_LERROR macro](nf-wiautil-wias_lerror.md) | The WIAS_LERROR macro is obsolete for Windows Vista and later. It is recommended that the WIAS_ERROR macro be used instead.The WIAS_LERROR macro writes a diagnostic WIA_ERROR message to the log file. |
| [WIAS_LHRESULT macro](nf-wiautil-wias_lhresult.md) | The WIAS_LHRESULT macro is obsolete for Windows Vista and later. It is recommended that the WIAS_HRESULT macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file. |
| [WIAS_LTRACE macro](nf-wiautil-wias_ltrace.md) | The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the WIAS_TRACE macro be used instead.The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file. |
| [WIAS_LWARNING macro](nf-wiautil-wias_lwarning.md) | The WIAS_LWARNING macro is obsolete for Windows Vista and later.The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file. |
| [WIAS_TRACE macro](nf-wiautil-wias_trace.md) | The WIAS_TRACE macro writes a diagnostic message to the Wiatrace.log file. |
| [wiauDbgHelper macro](nf-wiautil-wiaudbghelper.md) | The wiauDbgHelper function formats a message and writes it to a log file, or debugger, or both. |
| [wiauDbgInit macro](nf-wiautil-wiaudbginit.md) | The wiauDbgInit function initializes WIA debugging. |
| [wiauDbgSetFlags macro](nf-wiautil-wiaudbgsetflags.md) | The wiauDbgSetFlags function sets debugging flags. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [CWiauDbgFn::CWiauDbgFn method](nf-wiautil-cwiaudbgfn-cwiaudbgfn.md) | The CWiauDbgFn |
| [CWiauDbgFn::~CWiauDbgFn method](nf-wiautil-cwiaudbgfn-~cwiaudbgfn.md) | The CWiauDbgFn |
| [CWiauFormatConverter::CWiauFormatConverter method](nf-wiautil-cwiauformatconverter-cwiauformatconverter.md) | The CWiauFormatConverter |
| [CWiauFormatConverter::ConvertToBmp method](nf-wiautil-cwiauformatconverter-converttobmp.md) | The CWiauFormatConverter |
| [CWiauFormatConverter::Init method](nf-wiautil-cwiauformatconverter-init.md) | The CWiauFormatConverter |
| [CWiauFormatConverter::IsFormatSupported method](nf-wiautil-cwiauformatconverter-isformatsupported.md) | The CWiauFormatConverter |
| [CWiauFormatConverter::~CWiauFormatConverter method](nf-wiautil-cwiauformatconverter-~cwiauformatconverter.md) | The CWiauFormatConverter |
| [CWiauPropertyList::CWiauPropertyList method](nf-wiautil-cwiaupropertylist-cwiaupropertylist.md) | The CWiauPropertyList |
| [CWiauPropertyList::DefineProperty method](nf-wiautil-cwiaupropertylist-defineproperty.md) | The CWiauPropertyList |
| [CWiauPropertyList::GetPropId method](nf-wiautil-cwiaupropertylist-getpropid.md) | The CWiauPropertyList |
| [CWiauPropertyList::Init method](nf-wiautil-cwiaupropertylist-init.md) | The CWiauPropertyList |
| [CWiauPropertyList::LookupPropId method](nf-wiautil-cwiaupropertylist-lookuppropid.md) | The CWiauPropertyList |
| [CWiauPropertyList::SendToWia method](nf-wiautil-cwiaupropertylist-sendtowia.md) | The CWiauPropertyList |
| [CWiauPropertyList::SetAccessSubType method](nf-wiautil-cwiaupropertylist-setaccesssubtype.md) | The CWiauPropertyList |
| [CWiauPropertyList::SetCurrentValue method](nf-wiautil-cwiaupropertylist-setcurrentvalue.md) | The CWiauPropertyList |
| [CWiauPropertyList::SetValidValues method](nf-wiautil-cwiaupropertylist-setvalidvalues.md) | The CWiauPropertyList |
| [CWiauPropertyList::~CWiauPropertyList method](nf-wiautil-cwiaupropertylist-~cwiaupropertylist.md) | The CWiauPropertyList |
