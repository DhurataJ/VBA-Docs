---
title: SharedWorkspaceFile.ModifiedDate property (Office)
keywords: vbaof11.chm266005
f1_keywords:
- vbaof11.chm266005
ms.prod: office
api_name:
- Office.SharedWorkspaceFile.ModifiedDate
ms.assetid: c4d0f54c-db16-8a1e-a5d0-56ec9d5287fa
ms.date: 01/24/2019
ms.localizationpriority: medium
---


# SharedWorkspaceFile.ModifiedDate property (Office)

Gets the date and time when the **SharedWorkspaceFile** object was last modified. Read-only.

> [!NOTE] 
> Beginning with Microsoft Office 2010, this object or member has been deprecated and should not be used.


## Syntax

_expression_.**ModifiedDate**

_expression_ A variable that represents a **[SharedWorkspaceFile](Office.SharedWorkspaceFile.md)** object.


## Return value

Variant


## Example

The following example returns a list of shared workspace files whose date and time last modified is earlier than today.


```vb
Dim swsFile As Office.SharedWorkspaceFile 
    Dim dtmMidnight As Date 
    Dim dtmFileDate As Date 
    Dim strOlderFiles As String 
    dtmMidnight = CDate(FormatDateTime(Now, vbShortDate) & " 12:00:00 am") 
    For Each swsFile In ActiveWorkbook.SharedWorkspace.Files 
        dtmFileDate = swsFile.ModifiedDate 
        If dtmFileDate < dtmMidnight Then 
            strOlderFiles = strOlderFiles & swsFile.URL & vbCrLf 
        End If 
    Next 
    MsgBox "Files not modified today: " & vbCrLf & strOlderFiles, _ 
        vbInformation + vbOKOnly, "Older Files" 
    Set swsFile = Nothing
```


## See also

- [SharedWorkspaceFile object members](overview/Library-Reference/sharedworkspacefile-members-office.md)



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]