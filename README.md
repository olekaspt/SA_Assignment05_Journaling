# SA_Assignment05_Journaling

# SA_Assignment05

## Estimate

Read the entire assignment and calculate you estimate for the estimation assignment.

## Journaling

Using Repo https://github.com/olekaspt/SoftwareArchitectureCLassApplication.git

The goal of the code is to to be able the run the main exe with the option 1 (you may have to setup the debug options).  So that when this runs, it will create 
SampleJournal.txt that looks like SampleJournal.cpp.

By default, the journal file gets recorded to SampleJournal.txt so when you rebuild you don't compile errors after running.

There are three issues that need to be fixed.
1. Strings that contain \ need to be escaped with an extra \
2. Boolean input params need to be journaled
3. Integer input params need to be journaled.

You know you got it right when you can run the program and copy the txt file to the cpp file, and then it builds and runs :)

Code submission is to provide the provide the directory containing the  Journal library.  As simple zip of this directory is suffice.

PDF
1. Modify UI::PerformSampleJournalingPartsOps to be below:

```c++
void UI::PerformSampleJournalingPartsOps()
{
	// This is just mimic'ing a simple CAD workflow.
	// We are going to pretend the user makes  part, makes a widget feature, saves the part,
	// and then exits.  And this will stop the GUI loop and lead to exit on main
  Application::PartFile* partFile = MakePartUI("d:\\workdir\\someDir\\SomeName.part");
	//Setup Journaling File
	SetJournalingLangauge(JournalingLanguage::CPP);
	StartJournaling(BasePath() +"\\JournaledCPPFileProject\\SampleJournal.txt");


	
	AddWidgetFeatureToPartUI(partFile, true, 10);
	SavePartUI(partFile);

	Application::PartFile* partFile2 = OpenPartUI(BasePath() + "\\SampleVersionUp.prt");

	SavePartUI(partFile2);

	//End Journaling
	EndJournaling();
}
```

Look at the journal txt file.  What happened?  Briefly describe what we need to do to resolve this?





