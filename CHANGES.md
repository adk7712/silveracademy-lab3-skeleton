# Lab 3 skeleton – changes

## Step 1: Setup
- Created `lab3-skeleton/`; unzipped `lab3_ai_generated_skeleton.zip` into it (apps/, packages/, functions/, firebase/).

## Step 2: Renamed to .tsx
- apps/mobile/src/boundary/RootNavigator.ts -> RootNavigator.tsx
- apps/mobile/src/boundary/MainShell.ts -> MainShell.tsx
- apps/mobile/src/boundary/FeatureScreens.ts -> FeatureScreens.tsx
- apps/web/src/boundary/App.ts -> App.tsx
- apps/web/src/boundary/FeaturePages.ts -> FeaturePages.tsx

## Step 3: Duplicate marker added (first line)
- apps/mobile/src/module/ClientRepository.ts
- apps/web/src/module/ClientRepository.ts
- apps/mobile/src/control/useFeature.ts
- apps/web/src/control/useFeature.ts

## Step 4: New feature hooks
- apps/mobile/src/control/useLearnerDiscover.ts
- apps/mobile/src/control/useWallet.ts

## Step 5: Entity files grouped (26 files, verified)
- packages/shared/src/entity/accounts/: User.ts, InstructorProfile.ts, UserPrefs.ts
- packages/shared/src/entity/workshops/: Workshop.ts, WorkshopSnapshot.ts, Booking.ts, Attendance.ts, Feedback.ts, VolunteerAssignment.ts
- packages/shared/src/entity/venues/: Facility.ts, TimeSlot.ts, VenueRequest.ts, VenueRequestWorkshopSummary.ts, VenueSnapshot.ts
- packages/shared/src/entity/vouchers/: Wallet.ts, LedgerEntry.ts, VoucherTier.ts, VoucherInventoryItem.ts, VoucherUpload.ts, RejectedUploadRow.ts
- packages/shared/src/entity/reports/: Incident.ts, IncidentAttachment.ts, Notification.ts, AuditLog.ts
- packages/shared/src/entity/shared/: Timestamps.ts, Versioned.ts

## Step 6: Start-up class comment
- apps/mobile/src/boundary/RootNavigator.tsx (first line)

## Step 7: JSDoc on every class
- All 26 entity files: JSDoc + `export interface <Name>` with original TODO and `// TODO: fields from the class diagram`.
  Page numbers taken from the text of the class-diagram PDF: p. 66 User, InstructorProfile, Workshop, Booking, Attendance, Feedback, VolunteerAssignment, Timestamps, Versioned; p. 67 Facility, TimeSlot, VenueRequest, VenueRequestWorkshopSummary, VenueSnapshot; p. 68 Wallet, LedgerEntry, VoucherTier, VoucherInventoryItem, VoucherUpload, RejectedUploadRow; p. 69 Incident, IncidentAttachment, Notification, AuditLog, UserPrefs, WorkshopSnapshot. (This differs from the brief's "p. 66 for accounts/workshops/venues" rule; verify against your diagram.)
- 13 non-entity files (apps/mobile + apps/web boundary/control/module files, functions/src/**): JSDoc "(p. 65)", original TODO, `export {};`.
  Kinds: boundary = RootNavigator, MainShell, FeatureScreens, App, FeaturePages, CallableHandlers; control = useFeature (x2), PureDecisionModules; module = ClientRepository (x2), BackendRepositories, FirebaseSdkClients.
- ClientRepository.ts description had no " - " separator, so the full TODO text was used.

## Step 8: Config and Firebase rules
- Created package.json, tsconfig.json (root)
- firebase/boundary/FirestoreRules.ts -> firestore.rules; StorageRules.ts -> storage.rules (single TODO comment line each)
- Created firebase/firebase.json

## Step 9: Compile check
- `npm install` (adds node_modules/, package-lock.json); `npx tsc --noEmit` exits 0 with 41 source files checked. No fixes were needed.

## Step 10: Reports
- FOLDER_TREE.txt, CHANGES.md
