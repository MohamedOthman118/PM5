# UI & reliability refresh

This pass moves the workspace toward a lighter Monday.com / Apple-inspired interface while keeping the existing planning features.

## UX changes
- Table is now the default workspace view.
- Light project rail, softer borders/shadows, system font stack, and Monday-style blue primary actions.
- Reduced header clutter by moving presentation/import actions into the project menu.
- Compact project health cards for progress, blocked work, due-soon work, and overdue work.
- Added work-focus filters: all, open, due in 14 days, overdue, blocked/waiting, and completed.
- Search now includes task notes in addition to task name, owner, and ID.
- Added task duplication and one-click “Mark done”.
- Board-column add buttons now create tasks with the selected column status.
- Manager/presentation view now matches the lighter product UI.

## Reliability fixes
- Deleting a parent task now recursively deletes all nested descendants and removes dependency references.
- Status and progress remain consistent when moving tasks into/out of Done.
- Missing dependency IDs no longer leave tasks permanently blocked.
- Clipboard copy has a fallback for environments where `navigator.clipboard` is unavailable.
- Added the missing R2 image-serving route for uploaded team avatars.
- Team image uploads now accept only JPEG, PNG, and WebP.
