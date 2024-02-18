#include <iostream>
using namespace std;
#include <vector>
#include <string>
#include <iomanip> // For std

// Define a struct to hold the milk information for each session
struct MilkingSession {
    std::string cowid; // Unique 3digit identity code for every each cow
    double yield;      // Volume of milk record in litres
};

// Function to add a milk session record
void addMilkingSession(std::vector<MilkingSession>& sessions, const std::string& cowID, double yield) {
    sessions.push_back(MilkingSession{cowID, yield});
}

// Function to display all recorded milking sessions
void displayMilkingSessions(const std::vector<MilkingSession>& sessions) {
    std::cout << "Recorded Milking Sessions:\n";
    for (const auto& session : sessions) {
        std::cout << "Cow id: " << session.cowid
                  << ", Yield: " << std::fixed << std::setprecision(1) << session.yield << " litres\n";
    }
}

int main() {
    std::vector<MilkingSession> milkingSessions;

    // Example: Adding milking session records
    addMilkingSession(milkingSessions, "001", 10.5);
    addMilkingSession(milkingSessions, "002", 12.3);
    // Additional records can be added here

    // Display all recorded milking sessions
    displayMilkingSessions(milkingSessions);

    return 0;
}
