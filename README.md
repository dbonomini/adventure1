# adventure1
a program of hoping you survive

// My Program

#include <iostream>
#include <string>
#include <chrono>
#include <thread>
#include <cstdlib>
#include<ctime>

using namespace std;

int main() {

	// initial setup for advanced stats mode
	bool debug = true;

	// play game or kill program, program wait will be used throughout
	while (true) {
		
		cout << "Would you like to play? Type 'y' for yes or 'n' for no.\n";
		string play;
		cin >> play;

		if (play == "y") {

			// seeding ran num generator and declaring health
			srand(time(0));
			int health = 10;

			// welcome player and optional advanced stats mode
			cout << "Welcome Player 1.\n";
			cout << "would you like to play in advanced stats mode, y or n?\n";
				string advStat;
				cin >> advStat;
					if (advStat == "y"){

						int counter = rand() % 10;

						// do-while loop to cut out program after random number of times
						do {
							// set up game program with adv stats mode
							int attack = rand() % 5;
							int block = rand() % 5;
							cout << "Attack = " << attack << endl;
							this_thread::sleep_for(chrono::milliseconds(500));
							cout << "Block = " << block << endl;
							this_thread::sleep_for(chrono::milliseconds(500));
							if (block >= attack) {
								cout << "Successful Block!\n";
								this_thread::sleep_for(chrono::milliseconds(1500));
							}

							else {
								cout << "You Have Been Hit!\n";
								this_thread::sleep_for(chrono::milliseconds(1500));

								// Taking away health and displaying result for player
								health -= attack;
								cout << "Health Remaining: " << health << endl;
								this_thread::sleep_for(chrono::milliseconds(2000));

								// Nested if to tell you to go to the doctor and end program if needed
								if (health <= 0) {
									cout << "Player 1 has died... RIP\n";
									this_thread::sleep_for(chrono::milliseconds(5000));
									return 0;

								}
								else if (health <= 3) {
									cout << "LOW LIFE, GO SEE A DOCTOR!!!\n";
									this_thread::sleep_for(chrono::milliseconds(2000));
								}
								else {
									cout << "Keep Going Buddy!!\n";
									this_thread::sleep_for(chrono::milliseconds(1000));
								}

							}

							counter++;
						}
							while (counter <= 10);
						
						// inform player of victory
						cout << "CONGRATULATIONS PLAYER YOU HAVE DONE THE IMPOSSIBLE AND SURVIVED\n";
						this_thread::sleep_for(chrono::milliseconds(3000));
						cout << "Please play again sometime...\n";
						this_thread::sleep_for(chrono::milliseconds(2000));
					}
					else if (advStat == "n"){

						int counter = rand() % 10;

						// do-while loop to cut out program after random number of times
						do {
							// set up game program with adv stats mode
							int attack = rand() % 5;
							int block = rand() % 5;
							

							if (block >= attack) {
								cout << "Successful Block!\n";
								this_thread::sleep_for(chrono::milliseconds(1500));
							}

							else {
								cout << "You Have Been Hit!\n";
								this_thread::sleep_for(chrono::milliseconds(1500));

								// Taking away health and displaying result for player
								health -= attack;
								cout << "Health Remaining: " << health << endl;
								this_thread::sleep_for(chrono::milliseconds(2000));

								// Nested if to tell you to go to the doctor and end program if needed
								if (health <= 0) {
									cout << "Player 1 has died... RIP\n";
									this_thread::sleep_for(chrono::milliseconds(5000));
									return 0;

								}
								else if (health <= 3) {
									cout << "LOW LIFE, GO SEE A DOCTOR!!!\n";
									this_thread::sleep_for(chrono::milliseconds(2000));
								}
								else {
									cout << "Keep Going Buddy!!\n";
									this_thread::sleep_for(chrono::milliseconds(1000));
								}

							}

							counter++;
						} while (counter <= 10);

						// inform player of victory
						cout << "CONGRATULATIONS PLAYER YOU HAVE DONE THE IMPOSSIBLE AND SURVIVED\n";
						this_thread::sleep_for(chrono::milliseconds(3000));
						cout << "Please play again sometime...\n";
						this_thread::sleep_for(chrono::milliseconds(2000));

					}

					else {
						cout << "Response was invalid, sorry...\n";
						this_thread::sleep_for(chrono::milliseconds(3000));
					}

			

		}


		else if (play == "n") {
			cout << "Peace Out Buddy.\n";
			this_thread::sleep_for(chrono::milliseconds(2000));
			break;
		}

		else {
			cout << "Sorry Pal, invalid choice.\n";
			this_thread::sleep_for(chrono::milliseconds(2000));
		}
	}
}
