<template>
    <div class="form-handling">
        <h2>Form Handling</h2><hr/>
        <div class="job-form">
            <h3>Job Applicant Form</h3>
            <form v-on:submit.prevent="submitForm">
                <div>
                    <label for="name">Name</label>
                    <input type="text" id="name" v-model.trim.lazy="formData.name" />
                </div>
                <div>
                    <label for="profile">Profile Summary</label>
                    <textarea rows="5" id="profile" v-model.trim.lazy="formData.profileSummary"></textarea>
                </div>
                <div>
                    <label for="country">Country</label>
                    <select id="country" v-model="formData.country">
                        <option value="">Select a country</option>
                        <option value="Bharat">Bharat</option>
                        <option value="Israel">Israel</option>
                        <option value="Russia">Russia</option>
                    </select>
                </div>
                <div>
                    <label for="jobLocation">Job Location</label>
                    <select id="jobLocation" multiple v-model.lazy="formData.jobLocation">
                        <option value="Bharat">Bharat</option>
                        <option value="Israel">Israel</option>
                        <option value="Russia">Russia</option>
                        <option value="China">China</option>
                    </select>
                </div>
                <div>
                    <input type="checkbox" id="remoteWork" v-model="formData.remoteWork" true-value="Yes" false-value="No" />
                    <label for="remoteWork">Open to work remotely?</label>
                </div>
                <div>
                    <label>Skill Set</label>
                    <input type="checkbox" value="VueJS" id="vuejs" v-model="formData.skillSet" />
                    <label for="vuejs">VueJS</label>
                    <input type="checkbox" value="NodeJS" id="nodejs" v-model="formData.skillSet" />
                    <label for="nodejs">NodeJS</label>
                    <input type="checkbox" value="MongoDB" id="mongodb" v-model="formData.skillSet" />
                    <label for="mongodb">MongoDB</label>
                </div>
                <div>
                    <label>Years of Experience</label>
                    <input type="radio" value="0-2" id="0-2" v-model="formData.yearsOfExperience" />
                    <label for="0-2">0-2</label>
                    <input type="radio" value="2-5" id="2-5" v-model="formData.yearsOfExperience" />
                    <label for="2-5">2-5</label>
                    <input type="radio" value="5-10" id="5-10" v-model="formData.yearsOfExperience" />
                    <label for="5-10">5-10</label>
                    <input type="radio" value="10+" id="10+" v-model="formData.yearsOfExperience" />
                    <label for="10+">10+</label>
                </div>
                <div>
                    <label for="age">Age:</label>
                    <input v-on:keyup.enter="submitForm" type="number" id="age" v-model="formData.age" />
                </div>
                <button>Submit</button>
            </form>
        </div>
        <div class="form-data" v-if="formDataVisible">
            <h3>Form Data</h3>
            <table>
                <tr>
                    <th>Name</th>
                    <td>{{ formData.name }}</td>
                </tr>
                <tr>
                    <th>Profile Summary</th>
                    <td>{{ formData.profileSummary }}</td>
                </tr>
                <tr>
                    <th>Country</th>
                    <td>{{ formData.country }}</td>
                </tr>
                <tr>
                    <th>Job Location</th>
                    <td>{{ formData.jobLocation }}</td>
                </tr>
                <tr>
                    <th>Open to work remotely?</th>
                    <td>{{ formData.remoteWork }}</td>
                </tr>
                <tr>
                    <th>Skill Set</th>
                    <td>{{ formData.skillSet }}</td>
                </tr>
                <tr>
                    <th>Years Of Experience</th>
                    <td>{{ formData.yearsOfExperience }}</td>
                </tr>
                <tr>
                    <th>Age</th>
                    <td>{{ formData.age }}</td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'FormHandling',
    data() {
        return {
            formData: {
                name: '',
                profileSummary: '',
                country: '',
                jobLocation: [],
                remoteWork: 'No',
                skillSet: [],
                yearsOfExperience: '',
                age: null
            },
            formDataVisible: false,
        }
    },
    methods: {
        submitForm(event) {
            this.formDataVisible = true
        }
    }
}
</script>

<style scoped>
.form-handling {
    clear: both;
}
.job-form {
    width: 400px;
    display: block;
    margin-bottom: 20px;
    float: left;
}
.job-form label {
    width: 100%;
    font-size: 14px;
    font-weight: 600;
}
.job-form input[type="text"], .job-form textarea {
    width: 100%;
    font-size: 13px;
    padding: 6px 12px;
    margin-bottom: 20px;
    display: inline-block;
}
.job-form select {
    width: 100%;
    font-size: 14px;
    padding: 6px 12px;
    margin-bottom: 20px;
}
.job-form select option {
    font-size: 14px;
    padding: 6px 12px;
}
.job-form button {
    font-size: 14px;
    padding: 8px 16px;
    margin-top: 10px;
    color: #fff;
    background-color: darkblue;
    border: 1px solid darkblue;
}
.form-data {
    width: 50%;
    float: right;
}
.form-data table {
    border-collapse: collapse;
}
.form-data table th, .form-data table td {
    border: 1px solid #333;
    padding: 6px 12px;
    font-size: 14px;
}
</style>