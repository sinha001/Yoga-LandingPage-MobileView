<template>
    <div class="container hero-section">
        <div class="row">
            <div class="col-12 col-md-6 col-pad">
                <div class="hero-text">
                    <h5 class="head3">TRANSFORM LIVES</h5>
                    <h2 class="head2"> Become a certified <br /> Yoga Teacher in Rishikesh</h2>
                </div>
                <div class="mt-4">
                    <span class="span-head">Unlock your full potential with our 200 Hour Yoga<br />Alliance Certified Training. Limited spots!</span>
                </div>

                <!-- Flex container for buttons and ratings in the same row -->
                <div class="d-flex flex-wrap align-items-center justify-content-between mt-4 gap-3">
                    <div class="d-flex gap-3">
                        <button class="btn-1">Apply Now</button>
                        <button class="btn-2">
                            <img src="../assets/Images/line-md_downloading-loop.png" width="28" height="28" />
                            Download Syllabus
                        </button>
                    </div>

                    <div class="Frame-1045 mt-4 d-flex align-items-center gap-3 mb-2">
                        <img class="ratings" src="../assets/Images/tripadvisor rating.png" width="135px" height="43px" />
                        <img class="ratings" src="../assets/Images/google ratings.png" width="86.16px" height="45px" />
                        <img class="ratings" src="../assets/Images/Frame 1046.png" width="116px" height="45px" />

                    </div>

                </div>
            </div>

            <div class="col-12 d-flex justify-content-center image-container p-0">
                <img src="../assets/Images/Rectangle 6875 (1).png" class="img-fluid hero-image" />
            </div>
            
        </div>

    </div>
</template>

<style scoped>
.hero-section{
    padding-top: 120px;    
}
.col-pad {
    padding: 40px 20px;
}

.head3 {
    font-size: 14px;
    color: #FF5E14;
}

.head2 {
    font-size: 36px;
    letter-spacing: -0.5px;
    color: #734875;
}

.span-head {
    font-size: 16px;
    color: #455A64;
    letter-spacing: 0;
}

.head2, .head3, .span-head {
    font-weight: 400;
}

.btn-1 {
    background-color: #FF5E14;
    color: #FFFFFF;
    font-size: 16px;
    font-weight: 600;
    padding: 10px 22px;
    border: none;
    border-radius: 12px;
    letter-spacing: 0;
}

.btn-2 {
    color: #734875;
    font-size: 16px;
    font-weight: 600;
    padding: 8px 6px;
    border: 1px solid #734875;
    border-radius: 12px;
    display: flex;
    align-items: center;
    gap: 5px;
    letter-spacing: 0;
    background-color: #FFFFFF;
    box-shadow: 0 0 2px 0 #734875;
}

.Frame-1045{
    z-index: 1;
}
.image-container{
    margin-top: -75px;
    z-index:0;
}

.hero-image {
    max-width: 100%;  /* Adjust width to prevent overflow */
    height: auto;
    display: block;
}



/* Ensure the divs stay in the same row on all screen sizes */
@media (max-width: 768px) {
    .d-flex {
        flex-wrap: wrap;
        justify-content: center;
    }
}
</style>
