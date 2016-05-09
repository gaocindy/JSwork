var webFolder = [1,2,5,7,10,15,18,22,23,25,34,35,40,42,45,48,50];
var qaFolder = [2,5,10,12,16,17,24,38,40,47];
var aqaFolder = [2,8,10,11,13,17,20,33,36,49];
var mobileFolder = [2,3,4,5,8,15,17,22,30,32,35,45,49];

//just assume the four folders with stuendts ID are all set down

var stuNum = 0;
var jobAppTime = 1; // to store the job application, between 1 to 4
var idealList = []; // set four empty arrays to store results
var secondChoice = [];
var thirdChoice = [];
var outOfGame = [];

var compareNum = function(cadiNum){
    while (stuNum === cadiNum )  {
        jobAppTime++ ;
    }
};// Check if the student ID in webFolder can be find in other folders

for(var i = 0; i<webFolder.length; i++){
    stuNum = webFolder[i];
    qaFolder.forEach(compareNum); // search stuNum in other 3 folders
    aqaFolder.forEach(compareNum);
    mobileFolder.forEach(compareNum);

    switch(jobAppTime){
        case 1:
            idealList.push(stuNum);
            break;
        case 2:
            secondChoice.push(stuNum);
            break;
        case 3:
            thirdChoice.push(stuNum);
            break;
        case 4:
            outOfGame.push(stuNum);
    } // add student ID to different array based on the time of job application

    jobAppTime = 1; // set job application to 1 for next loop
}

console.log('The ideal candidates of students are '+ idealList); // print out 4 lists
console.log('The second choice of students are ' + secondChoice);
console.log('The third choice of studnets are '+ thirdChoice);
console.log('Students already out of game ' + outOfGame);