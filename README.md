# Crime-Analysis-
# Crime Reporting System
def display_menu():
    print("\nCrime Reporting System")
    print("1. Add a Crime Report")
    print("2. View All Reports")
    print("3. Crime Analysis")
    print("4. Exit")

def add_crime_report(crime_reports):
    crime_type = input("Enter the type of crime (e.g., theft, vandalism): ")
    location = input("Enter the location of the crime: ")
    date = input("Enter the date of the crime (e.g., 2024-12-20): ")
    description = input("Enter a description of the crime: ")
    report = {
        "crime_type": crime_type,
        "location": location,
        "date": date,
        "description": description
    }
    crime_reports.append(report)
    print("Crime report added successfully!")

def view_all_reports(crime_reports):
    print("\nAll Crime Reports:")
    for index, report in enumerate(crime_reports, start=1):
        print(f"\nReport {index}:")
        print(f"Type: {report['crime_type']}")
        print(f"Location: {report['location']}")
        print(f"Date: {report['date']}")
        print(f"Description: {report['description']}")

def crime_analysis(crime_reports):
    analysis = {}
    for report in crime_reports:
        crime_type = report["crime_type"]
        analysis[crime_type] = analysis.get(crime_type, 0) + 1
    print("\nCrime Analysis Report:")
    for crime_type, count in analysis.items():
        print(f"{crime_type}: {count} occurrence(s)")

def main():
    crime_reports = []
    while True:
        display_menu()
        choice = input("Enter your choice (1-4): ")
        if choice == "1":
            add_crime_report(crime_reports)
        elif choice == "2":
            view_all_reports(crime_reports)
        elif choice == "3":
            crime_analysis(crime_reports)
        elif choice == "4":
            print("Exiting the system. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
