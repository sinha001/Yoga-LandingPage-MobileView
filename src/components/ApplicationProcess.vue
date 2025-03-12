<template>
    <div class="application-section">
        <p class="section-highlight">APPLICATION PROCESS</p>
        <h2 class="section-title">Start your yoga career in 3 Simple Steps</h2>
        <p class="section-subtitle">
            Getting started with yoga has never been easier! Follow these quick steps to begin your path to mindfulness, 
            flexibility, and inner peace.
        </p>

        <div class="steps-container">
            <div class="step" v-for="(step, index) in steps" :key="index">
                <!-- Left Column: Step Number & Connecting Line -->
                <div class="step-left">
                    <div class="step-number" :class="{ 'first-step-number': index === 0, 'other-step-number': index !== 0 }">
                        {{ step.number }}
                    </div>
                    <div 
                        v-if="index !== steps.length - 1" 
                        class="step-line" 
                        :class="{ 'first-step-line': index === 0, 'other-step-line': index !== 0 }"
                    ></div>
                </div>

                <!-- Right Column: Step Box -->
                <div class="step-right">
                    <div class="step-content">
                        <h3 class="step-title">{{ step.title }}</h3>
                        <p class="step-description">{{ step.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            steps: [
                {
                    number: "01",
                    title: "Fill Out the Application Form",
                    description: "Browse our selection of Online Yoga Teacher Training Courses to find the one that best suits your goals."
                },
                {
                    number: "02",
                    title: "Speak with Our Admission Advisor",
                    description: "Get guidance on course details, travel, and what to expect."
                },
                {
                    number: "03",
                    title: "Reserve Your Spot with $200",
                    description: "Secure your seat with a small deposit. The remaining fee is payable upon arrival."
                }
            ]
        };
    }
};
</script>

<style scoped>
.application-section {
    padding: 48px 24px;
    background-color: #FFFFFF;
    text-align: start;
}

.section-highlight {
    color: #FF6600;
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 1px;
    margin-bottom: 8px;
}

.section-title {
    font-size: 36px;
    color: #4F2553;
    font-weight: 400;
    margin-bottom: 24px;
    letter-spacing: 0;
}

.section-subtitle {
    color: #455A64;
    font-weight: 400;
    letter-spacing: 0;
    margin-bottom: 24px;
}

/* Steps Layout */
.steps-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
}

.step {
    display: flex;
    justify-items: center;
    width: 100%;
    max-width: 450px;
    position: relative;
    gap:24px;
}

/* Left Column: Step Number & Connecting Line */
.step-left {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    width: 50px;
    top: 20px;
    
}

/* Step Number Styling */
.step-number {
    color: white;
    font-size: 12px;
    font-weight: bold;
    width: 34px;
    height: 34px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    position: relative;
    z-index: 1;
    border: 1px solid white;
}

/* Step 01 Number */
.first-step-number {
    background: #4F2553;
}

/* Steps 02 & 03 Number */
.other-step-number {
    background: #FF6600;
}

/* Timeline Line */
.step-line {
    width: 2px;
    height: 140px;
    position: absolute;
    top: 20px;
}

/* Step 01 Line */
.first-step-line {
background: linear-gradient(to bottom, #4F2553 0%, #4F2553 50%, #FF6600 50%, #FF6600 100%);
}

/* Steps 02 & 03 Line */
.other-step-line {
    background-color: #FF6600;
}

/* Right Column: Step Box */
.step-right {
    flex-grow: 1;
    display: flex;
    align-items: center;
}

.step-content {
    background: white;
    border: 1px solid #FFB890;
    border-radius: 12px;
    padding: 16px;
    text-align: left;
    width: 100%;
    max-width: 320px;
    max-height: 130px;
    margin-bottom: 20px;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}

/* Step Title */
.step-title {
    font-size: 20px;
    font-weight: 500;
    letter-spacing: 0;
    color: #314650;
}

/* Step Description */
.step-description {
    font-size: 12px;
    color: #455A64;
    margin-top: 4px;
    font-family: 400;
    letter-spacing: 0;
}
</style>
