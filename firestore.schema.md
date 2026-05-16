# SmartAttend Firestore Schema

## Collections

- `users/{uid}`: `name`, `email`, `role`, `status`, `department`, `subject`, `assignedClasses[]`, `createdAt`, `updatedAt`
- `students/{studentId}`: `fullName`, `rollNumber`, `department`, `year`, `section`, `phone`, `email`, `status`, `attendancePercent`
- `teachers/{teacherId}`: `name`, `email`, `subject`, `assignedClasses[]`, `phone`, `status`
- `departments/{departmentId}`: `name`, `code`, `hod`
- `classes/{classId}`: `department`, `year`, `section`, `strength`, `active`
- `attendance_sessions/{sessionId}`: `teacherId`, `teacherName`, `subject`, `classId`, `department`, `year`, `section`, `date`, `timestamp`, `present`, `absent`, `locked`, `device`, `submittedAt`
- `attendance_records/{recordId}`: `sessionId`, `studentId`, `studentName`, `rollNumber`, `status`, `classId`, `subject`, `teacherId`, `date`
- `reports/{reportId}`: `type`, `actorId`, `actorName`, `classId`, `subject`, `message`, `sessionId`

## Recommended Indexes

- `attendance_sessions`: `classId ASC`, `subject ASC`, `date DESC`
- `attendance_sessions`: `teacherId ASC`, `date DESC`
- `attendance_records`: `studentId ASC`, `date DESC`
- `students`: `department ASC`, `year ASC`, `section ASC`, `status ASC`
