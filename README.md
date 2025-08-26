# Rhino Ride
This website is based on theme of western black rhinoceros which is declared to be extinct by thr IUCN in 2011.

# Interactive Elements

- A facts panel which states fact about the animal with a next and previous button for the user to get back to the previous text and go to next text and also there is an image display on the right hand side of the facts panel where images are animated to shift when the next or previous buttons are pressed by the user.
    [Implementation :- 
    - used array to store data
    - intialized values to be zeroth element of array
    - when next button is pressed increasing the value of data to be next element of array
    - when prev button is pressed ecreasing the value to respresent previous element of that data
    - ensuring the the array variable doesn't go out of bounds by changing its value whenever it reaches the maximum valyue for the array ]

- A footer which will tell the people that this is an endangered animal and also the letters of the endangered change to red and rotate by 360deg to make the website look more attaractive and also there is a link to wikipedia at the bottom of this for the readers who want to read mote about this animal.
    [Implementation:-
    - rotated the letters using transform and transition and the color effect by hover
    - increasing size of link by scale method
    ]

- A music hover button to play the sound of a rhino whenever it is clicked.
    [Implementation:-
    - using position fixed for the fixed position
    - playing and pausing audio when the button is pressed using javascript
    ] 

- After the slider reaches to 4th slide(which is the last slide) a button is made to be visible that takes to my virtual rhino that squishy the rhino.
    [Implementation:-
    - Used acounter varaible to check if the last slide is reached or not
    - diplay of button changed from none to block when last slide is reached
    - shaking effect added at button using animation property and hover effect
    - Used svelte:routing to link the main page and the virtual pet page via this button
    ]

- At the vertual animal page you can click on squishy to interact with it and at the 5th click you will find something amazing.
    [Implementation:-
    - Used gifs by making an array of links of these gifs and changing them whenver the gif is clicked
    - At the fifth tap implementing an easter egg by redirecting to another website 
    ]
