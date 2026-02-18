# =========================================
#      ATTENDANCE MANAGEMENT SYSTEM
# =========================================

students = []
attendance = []

def add_student():
    print("\n--- Add Student ---")
    id = input("Enter Student ID: ")
    name = input("Enter Student Name: ")
    student = {"id": id, "name": name}
    students.append(student)
    print("Student Added Successfully!")

def view_students():
    print("\n--- Student List ---")
    if len(students) == 0:
        print("No Students Found!")
    else:
        for s in students:
            print("ID:", s["id"], "| Name:", s["name"])

def mark_attendance():
    print("\n--- Mark Attendance ---")
    if len(students) == 0:
        print("No Students Found! Please Add Students First!")
    else:
        for s in students:
            print("Student:", s["name"])
            status = input("Enter Status (Present/Absent): ")
            record = {
                "id": s["id"],
                "name": s["name"],
                "status": status
            }
            attendance.append(record)
        print("Attendance Marked Successfully!")

def view_attendance():
    print("\n--- Attendance Records ---")
    if len(attendance) == 0:
        print("No Attendance Records Found!")
    else:
        for a in attendance:
            print("ID:", a["id"],
                  "| Name:", a["name"],
                  "| Status:", a["status"])

def view_report():
    print("\n--- Attendance Report ---")
    if len(attendance) == 0:
        print("No Attendance Records Found!")
    else:
        for s in students:
            present = 0
            absent = 0
            for a in attendance:
                if a["id"] == s["id"]:
                    if a["status"].lower() == "present":
                        present += 1
                    else:
                        absent += 1
            print("Name:", s["name"],
                  "| Present:", present,
                  "| Absent:", absent)

while True:
    print("\n=========================================")
    print("     ATTENDANCE MANAGEMENT SYSTEM")
    print("=========================================")
    print("  1. Add Student")
    print("  2. View All Students")
    print("  3. Mark Attendance")
    print("  4. View Attendance Records")
    print("  5. View Attendance Report")
    print("  6. Exit")
    print("=========================================")

    choice = input("Enter Your Choice: ")

    if choice == "1":
        add_student()
    elif choice == "2":
        view_students()
    elif choice == "3":
        mark_attendance()
    elif choice == "4":
        view_attendance()
    elif choice == "5":
        view_report()
    elif choice == "6":
        print("Thank You! Goodbye!")
        break
    else:
        print("Invalid Choice! Please Try Again!") this is my coding so generate as link or file to paste in ppt...
