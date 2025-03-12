<template>
    <div class="pricing-section">
        <p class="section-highlight">PRICING & PACKAGES</p>
        <h2 class="section-title">Residential Yoga Teacher Training</h2>

        <!-- ✅ Tab Switcher (Now Only One is Active) -->
        <div class="tab-switcher">
            <button v-for="(packageItem, index) in packages" :key="index" @click="selectPackage(packageItem)" :class="{
                'active-tab': selectedPackage.id === packageItem.id,
                'first-tab': index === 0,
                'last-tab': index === packages.length - 1
            }">
                {{ packageItem.hour }} Hour
            </button>
        </div>

        <!-- Pricing Card -->
        <div class="pricing-card">
            <div class="card-header">
                <img :src="selectedPackage.logo" alt="Yoga Certification" class="certification-logo">
                <div class="rating">
                    ⭐⭐⭐⭐✰<br>
                    <span class="rating-text">4.9 Rating (2.3k)</span>
                </div>
            </div>

            <h3 class="training-title">{{ selectedPackage.hour }} Hour Yoga Teacher Training</h3>

            <!-- Pricing Section -->
            <div class="pricing-container">
                <div class="pricing-box">
                    <p class="price-type">Private</p>
                    <div class="divider"></div>

                    <p class="price">${{ selectedPackage.privatePrice }} <span class="old-price">${{
                            selectedPackage.oldPrivatePrice }}</span></p>
                </div>
                <div class="pricing-box">
                    <p class="price-type">Sharing</p>
                    <div class="divider"></div>
                    <p class="price">${{ selectedPackage.sharedPrice }} <span class="old-price">${{
                            selectedPackage.oldSharedPrice }}</span></p>
                </div>
            </div>

            <!-- ✅ Divider Line After Pricing -->
            <div class="divider"></div>

            <!-- ✅ Features List (2 Columns) -->
            <div class="features">
                <ul>
                    <li v-for="(feature, index) in selectedPackage.features.slice(0, selectedPackage.features.length / 2)"
                        :key="'left-' + index">
                        <img src="../assets/Images/Group (2).png"/> {{ feature }}
                    </li>
                </ul>
                <ul>
                    <li v-for="(feature, index) in selectedPackage.features.slice(selectedPackage.features.length / 2)"
                        :key="'right-' + index">
                        <img src="../assets/Images/Group (2).png"/> {{ feature }}
                    </li>
                </ul>
            </div>

            <button class="cta-button">Get Started</button>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";
// Yoga Packages Data
const packages = ref([
    { id: 1, hour: "100", logo: new URL("../assets/Images/Rectangle 6811.png", import.meta.url).href, privatePrice: 799, oldPrivatePrice: 899, sharedPrice: 799, oldSharedPrice: 899, features: ["14 Days Stay & Meals", "Beginner Friendly", "Airport Pick & Drop", "Daily Veg Meals", "Yoga Alliance Certification", "Study Materials", "Lifetime Support & Mentorship", "Yoga Equipments"] },
    { id: 2, hour: "200", logo: new URL("../assets/Images/Rectangle 6811.png", import.meta.url).href, privatePrice: 999, oldPrivatePrice: 1499, sharedPrice: 999, oldSharedPrice: 1499, features: ["27 Days Stay & Meals", "Beginner to Advanced", "Airport Pick & Drop", "Daily Veg Meals", "Yoga Alliance Certification", "Study Materials", "Lifetime Support & Mentorship", "Yoga Equipments"] },
    { id: 3, hour: "300", logo: new URL("../assets/Images/300-rys.png", import.meta.url).href, privatePrice: 1149, oldPrivatePrice: 1649, sharedPrice: 1149, oldSharedPrice: 1649, features: ["27 Days Stay & Meals", "Advanced Training", "Airport Pick & Drop", "Daily Veg Meals", "Yoga Alliance Certification", "Study Materials", "Lifetime Support & Mentorship", "Yoga Equipments"] }
]);

// Default selected package
const selectedPackage = ref(packages.value[0]);

// Function to change selected package
const selectPackage = (packageItem) => {
    selectedPackage.value = packageItem;
};
</script>

<style scoped>
.pricing-section {
    padding: 48px 24px;
    background-color: #FFF8F4;
    text-align: center;
}

/* Section Header */
.section-highlight {
    color: #FF6600;
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 1px;
}

.section-title {
    font-size: 32px;
    color: #4F2553;
    font-weight: 400;
    margin-bottom: 24px;
    letter-spacing: -1px;
}

/* ✅ Tab Switcher */
.tab-switcher {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
    background: #EDE4E0;
    border-radius: 30px;
    overflow: hidden;
    width: fit-content;
    margin: 0 auto;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}

.tab-switcher button {
    background: transparent;
    border: 1px solid #4F2553;
    padding: 12px 20px;
    font-weight: 600;
    color: #4F2553;
    cursor: pointer;
    transition: 0.3s;
    border-right: none;
}

/* ✅ Fix for last button border */
.tab-switcher button:last-child {
    border-right: 1px solid #4F2553;
}

/* ✅ Rounded Corners for First & Last Buttons */
.first-tab {
    border-top-left-radius: 30px;
    border-bottom-left-radius: 30px;
}

.last-tab {
    border-top-right-radius: 30px;
    border-bottom-right-radius: 30px;
}

/* ✅ Active Tab (Fix applied here) */
.tab-switcher .active-tab {
    background: #4F2553;
    color: white;
}

/* Pricing Card */
.pricing-card {
    background: white;
    border: 1px solid #FFB890;
    border-radius: 12px;
    padding: 20px;
    text-align: left;
    max-width: 400px;
    margin: 20px auto;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}

/* Card Header */
.card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.certification-logo {
    width: 50px;
}

.rating-text {
    font-size: 12px;
    color: #666;
}

/* Training Title */
.training-title {
    font-size: 24px;
    font-weight: 500;
    color: #333;
    margin: 20px 0;
    letter-spacing: 0;
}

/* Features List */
.features {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    font-size: 14px;
    color: #333;
}

.features ul {
    width: 50%;
    list-style: none;
    padding: 0;
}

.features li {
    padding: 5px 0;
}

/* CTA Button */
.cta-button {
    width: 100%;
    background: #FF6600;
    color: white;
    padding: 12px;
    font-size: 16px;
    font-weight: bold;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    margin-top: 16px;
}

.cta-button:hover {
    background: #E65C00;
}

/* ✅ Pricing Section - Now Properly Aligned */
.pricing-container {
    display: flex;
    justify-content: space-between;
    margin-bottom: 16px;
}

.pricing-box {
    background: #FFF4EE;
    border-radius: 8px;
    padding: 12px;
    width: 48%;
    text-align: start;
    border: 1px solid #FFB890;
    margin-bottom: 0;
    padding-bottom: 0;
}

.price-type {
    font-size: 10px;
    color: #FF6600;
    font-weight: bold;
    margin-bottom: 0;
    padding-bottom: 0;
}

.price {
    font-size: 24px;
    font-weight: bold;
    letter-spacing: -1px;
    color: #333;
}

.old-price {
    font-size: 14px;
    color: #999;
    text-decoration: line-through;
    margin-left: 5px;
}

/* ✅ Divider After Pricing */
.divider {
    width: 100%;
    height: 1px;
    background: #F5AE64;
    margin: 20px 0;
}

/* ✅ Features List (Now in Two Columns) */
.features {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    font-size: 12px;
    font-family: 500;
    color: #333;
    margin-bottom: 20px;
}

.features ul {
    width: 48%;
    list-style: none;
    padding: 0;
}

.features li {
    padding: 5px 0;
}
</style>
